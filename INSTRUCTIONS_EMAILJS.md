# Instructions pour configurer l'envoi d'emails avec EmailJS

## Étape 1 : Créer un compte EmailJS

1. Allez sur https://www.emailjs.com/
2. Cliquez sur "Sign Up" et créez un compte gratuit (gratuit jusqu'à 200 emails/mois)
3. Confirmez votre email

## Étape 2 : Configurer un service email

1. Dans le dashboard EmailJS, allez dans "Email Services"
2. Cliquez sur "Add New Service"
3. Choisissez "Gmail" (ou votre fournisseur email)
4. Connectez votre compte email (emmanuelatcho@yahoo.com)
5. **Notez le SERVICE ID** (ex: service_xxxxxxx)

## Étape 3 : Créer un template d'email

1. Allez dans "Email Templates"
2. Cliquez sur "Create New Template"
3. Utilisez ce template :

```
Subject: Nouvelle inscription aux sessions gratuites - {{from_name}}

Bonjour,

Vous avez reçu une nouvelle inscription pour les sessions gratuites :

Nom complet: {{from_name}}
Email: {{from_email}}
Numéro WhatsApp: {{whatsapp}}
Sujet d'intérêt: {{sujet}}

Message:
{{message}}

---
Cet email a été envoyé automatiquement depuis le formulaire d'inscription du site web.
```

4. Dans "To Email", mettez: `emmanuelatcho@yahoo.com`
5. Dans "From Name", mettez: `{{from_name}}`
6. Dans "Reply To", mettez: `{{from_email}}`
7. **Notez le TEMPLATE ID** (ex: template_xxxxxxx)

## Étape 4 : Obtenir votre clé publique

1. Allez dans "Account" > "General"
2. Trouvez "Public Key"
3. **Copiez la PUBLIC KEY** (ex: xxxxxxxxxxxxxxxxxxxxxx)

## Étape 5 : Mettre à jour le code HTML

Dans le fichier `index.html`, remplacez les valeurs suivantes :

1. **Ligne ~900** : Remplacez `YOUR_PUBLIC_KEY` par votre clé publique
2. **Ligne ~932** : Remplacez `YOUR_SERVICE_ID` par votre Service ID
3. **Ligne ~932** : Remplacez `YOUR_TEMPLATE_ID` par votre Template ID

Exemple :
```javascript
emailjs.init("abc123xyz789"); // Votre clé publique

emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

## Test

1. Ouvrez votre site web
2. Remplissez le formulaire d'inscription
3. Soumettez le formulaire
4. Vérifiez que vous recevez l'email sur emmanuelatcho@yahoo.com

## Note importante

- Le plan gratuit d'EmailJS permet 200 emails/mois
- Pour plus d'emails, vous pouvez passer à un plan payant
- L'email sera envoyé automatiquement à chaque inscription

