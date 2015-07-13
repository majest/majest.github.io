---
layout: post
title:  "Using GPG as a secure method of transmitting sensitive data"
date:   2014-10-01 13:11:00
categories: libs
---

To improve the security standards all passwords, pem files, keys and other sensitive data can be encrypted using GPG. It’s generally not advised to send such data using open text via Skype, E-mail etc.

You should start by creating a key pair which will create an entry in your keychain. This command will generate key pair which is a secret and public key. Keep your secret key secure. Send your public key to a person you will be receiving the encrypted data from. 

$>gpg --gen-key


To recieve encrypted messages it's required to export a public key. This key then needs to be sent to sender who will be encrypting the message

$>gpg --export -a ag@pb.com > your_name-public.gpg


Usually encrypted messages are delivered as gpg or asc file where gpg files are delivered as binary and asc files are in plain text. To decrypt a message:

$>gpg -d encrypted_file

