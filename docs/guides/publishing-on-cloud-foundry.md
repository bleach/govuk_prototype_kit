# Publishing on the web (Cloud Foundry)

Cloud Foundry can be used to get your prototype online. It is an alternative to [Heroku](deploying-on-heroku.md). 

Once your prototype is on a Cloud Foundry installation, other people will be able to access and try your prototype from their own computers or mobile devices.

> **DO NOT** enter real user data in to prototypes hosted on Cloud Foundry. If your prototype stores or collects user data, talk to a security professional about appropriate security steps you must take.

A prototype deployed on Cloud Foundry is called an `app` - it will have a url
like: `your-prototype.domain` where the domain part will be different for each
provider. 
 - `your-prototype.cloudapps.digital` if deployed on the PaaS for Government 
 - `your-prototype.run.pivotal.io` if deployed on Pivotal Web Services

You can have multiple apps running on Cloud Foundry - projects often have several so they can try different ideas out at once.

## 1) Sign up with a Cloud Foundry provider

If you don't have access to a Cloud Foundry installation, you can search for Cloud Foundry providers using Google or on the Digital Marketplace.

Many providers offer a trial period during which you can deploy apps free of charge.

The [PaaS for
Government](https://www.gov.uk/government/publications/platform-as-a-service/platform-as-a-service)
is a Cloud Foundry installation that GDS provide for hosting government
services that is currently in private beta.

## 2) Install the Cloud Foundry CLI

Download and run the installer for your platfrom [from this
page](https://github.com/cloudfoundry/cli#downloads)

## 3) Login to Cloud Foundry

Log into Cloud Foundry, following the instructions from your Cloud Foundry provider.

## 4) Choose a name for your app.
Pick a name for your app. You need to choose a name that's unique. The name is used in the url for your prototype. For example: 
`govuk-payments-prototype` will create an app at:
`govuk-payments-prototype.domain`.

## 5) Push your app

You need to create an app on Cloud Foundry for each prototype you want to put on the web.

In the folder of your prototype, run:

```
cf push [NAME_OF_YOUR_APP] 
```
Replace `[NAME_OF_YOUR_APP]` with what you want to call your prototype.

## 6) Set a username and password

Prototypes made with the kit require a username and password when published online. This stops members of the public coming across your prototype by accident.

### To set username and password:

```
cf set-env [NAME_OF_YOUR_APP] USERNAME [username_here]
cf set-env [NAME_OF_YOUR_APP] PASSWORD [password_here]
cf restage [NAME_OF_YOUR_APP]
```

TODO: check if restart works as an alternative

## 7) View your prototype on the web

After your work is deployed, you will be able to view it on the web by visiting `[NAME_OF_YOUR_APP].domain`, where `domain` is the domain name used by your Cloud Foundry provider. If you are not sure what that is, or have forgotten what you called your app, you can find out by typing:

```
cf apps
```
which will list all your deployed apps and the hostnames on which they reside.

---
[Documentation index](../README.md)
