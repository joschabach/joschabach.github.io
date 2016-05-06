---
title: Some vague ideas on building a secure email service
tags:
- design requirements
- email alternative
- security
- encryption
excerpt: "A secure email service should not only encrypt messages end-to-end, but also meta-data. It should work without disclosing senders and recipients to third parties, and work asynchronously. Here is a possible solution."
---


In the wake of growing awareness of the indiscriminate spying activities of governments and private entities, more people consider moving away from existing email services, such as Gmail, Hotmail or even the accounts provided by employers and universities. Email is fundamentally broken: encryption comes with serious usability impediments (ever tried to sync your PGP encrypted mail across multiple devices), and your email provider is forced to hand the unencryptable meta-data (to, from, ip/location, subject, client etc.) to basically unaccountable government agencies. If you are involved with anything that might be affected by industrial espionage, or if you are interested in any form of political activism (such as Transparency International, Greenpeace, Amnesty International, Attac etc.), if you do not want to be blackmailed for your sexual preferences, your religion, etc., you should be very worried.


I am aware that our children use email less and less, but I am still hooked on it and think that it should continue to play a role in my life. So how could we design a better email service?

**Caveat: I am no security expert, I am likely missing important points, and any good idea I come up with here has very likely been already implemented somewhere.**


Any improvement over email should offer the following features:


1. Upward compatibility: the service should be able to use normal email as a fall-back solution and not break our existing workflows. This can be implemented in many ways, for instance by configuring it as a local proxy application that looks like a normal IMAP account to your existing desktop mail client. I will not go into details here.


2. There should be no usable meta-data at the service. The provider must not know what the message contains, what it is about, who receives it, and who sends it, and what graph senders and receivers form. (Some of these requirements are very difficult to meet.)


3. There must be protection against unsolicited messages (Spam) and Denial of Service attacks.


4. Recipients must be informed about available new messages in a timely fashion.


Existing public key/private key encryption can take care of the content of the message, and comfort problems with key exchange across devices can be slightly alleviated with clever applications. (Yes, there will always be successful hacking attempts, phishing, device backdoors etc. for targeted surveillance, but summary surveillance should become difficult).


We can protect senders and receivers by simply removing accounts and authentification altogether. All messages are stored as indiscriminate blobs of encrypted data, only distinguished by a nondescript unique identifier code. Every user may download any message, but will only be able to decrypt those that were encrypted with his or her public key. (Because decryption works only with the private key, the provider or third parties won't be able to discern the right recipient from the public key directory.) Every user may also upload arbitrary blobs of encoded data, together with a unique identifier. Our alternative email provider works basically like Rapidshare.


Unfortunately, the requirements \#2 and \#3 appear to be incompatible: protection against identification of senders and receivers also means that anonymous senders and receivers may sabotage the service by clogging it. This might be somewhat alleviated by using an anonymous ticketing system: users can buy tickets from a number of vendors, check their expiration at the central provider, exchange them freely against other tickets using anonymous services etc. Tickets work like cash and should be pretty hard to track. Every transaction with the email service will require the use of tickets, and if tickets cost actual money, they will deter indiscriminate spammers and make sure that the infrastructure of the service is adequate to its load.


Requirement \#4 seems to be the hardest to solve: if we no longer have per-recipient accounts, recipients won't know when new messages arrive, and how to identify them among all the data on the central email server. 
We will probably have to resort to the digital equivalent of clandestine communication in a Ian Fleming novel: dead drops. A dead drop is an arbitrary open storage somewhere, where the sender can leave a small notification containing the identifier of the actual message, and the recipient can regularly visit to check if new notifications arrived. 


Dead drops require that both sender and recipient agree on their location and/or the encryption of the notification, whereas third parties should be unable to match sender and recipient. I do not see a perfect solution for this problem, but two somewhat imperfect strategies come to mind: Obviously, sender and recipient could meet from time to time in person, and agree on a dead drop while nobody watches. However, this is not always practical, especially when initiating communication with people in other countries. In that case, we might use "public dead drops", at least for establishing the relationship. Each recipient will have a few (maybe thousands) of public dead drops, which are announced along with their public key. Public dead drops overlap, i.e. each one will be shared with hundreds of other users. As a result, recipients and messages are much harder to match for outside observers, but as a drawback, each recipient will have to download lots of messages that are not meant for her or him (but which cannot be decrypted using the private key of that user, of course). On the other hand, this (along with the longer message delay) might not pose much of a problem if the public dead drops are only used for announcing handshake messages.


There you go. What would you improve?

