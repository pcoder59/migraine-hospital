<template>
    <v-container>
        <h1>Contact Form</h1>
        <v-form v-model="valid" @submit.prevent="sendContact" v-if="sent == false">
            <v-text-field v-model="name" :rules="nameRules" label="Name" name="contact_name"></v-text-field>
            <v-text-field v-model="email" :rules="emailRules" label="Email" name="contact_email"></v-text-field>
            <v-text-field v-model.number="contact" :rules="contactRules" label="Contact Number" name="contact_number"></v-text-field>
            <v-textarea v-model="message" :rules="messageRules" label="Message" name="message"></v-textarea>
            <v-btn :disabled="!valid" type="submit" value="Send" @click="sendContact" color="primary">Send</v-btn>
        </v-form>
        <v-layout justify-center v-if="sent == true">
            <h1>Your Mail Has Been Sent</h1>
        </v-layout>
        <v-layout justify-center v-if="error == true">
            <h2>There was an error sending Your Email. Please Try Again!</h2>
        </v-layout>
        <v-layout justify-center v-if="sending == true">
            <h2>Your Email Is Being Sent... Please Wait...</h2>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            name: null,
            email: null,
            contact: null,
            message: null,
            valid: false,
            nameRules: [
                v => !!v || "Name is Required",
                v => /([a-z])\w+/.test(v) || "Name is Invalid"
            ],
            emailRules: [
                v => !!v || "Email is Required",
                v => /.+@.+\..+/.test(v) || "Enter a Valid Email"
            ],
            contactRules: [
                v => !!v || "Contact Number is Required",
                v => /^[0-9+]\d*$/.test(v) || "Phone Number is invalid",
            ],
            messageRules: [
                v => !!v || "Message is Required"
            ]
        }
    },
    computed: {
        sending: function() {
            return false;
        },
        sent: function() {
            return false;
        },
        error: function() {
            return false;
        }
    },
    methods: {
        sendContact(e) {
            this.sending = true;
            const self = this;
            emailjs.sendForm('contact_service', 'contact_form', e.target, 'user_lYBM45aIuAfPKnfWx0b5n').then(function(result) {
                self.sending = false;
                self.sent = true;
                self.error = false;
                console.log('SUCCESS!', result.status, result.text);
            }, function (error) {
                self.sending = false;
                self.sent = false;
                self.error = true;
                console.log('FAILED...', error);
            });
        }
    }
}
</script>

<style scoped>

</style>