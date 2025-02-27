<p align="center">
    <img alt="Parse Server" src="https://github.com/parse-community/parse-server/raw/master/.github/parse-server-logo.png" width="500">
  </a>
</p>

<p align="center">
  Parse Server is an open source backend that can be deployed to any infrastructure that can run Node.js.
</p>


<p align="center">
    <a href="https://twitter.com/intent/follow?screen_name=parseplatform"><img alt="Follow on Twitter" src="https://img.shields.io/twitter/follow/parseplatform?style=social&label=Follow"></a>
    <a href="https://github.com/parse-community/parse-server/actions?query=workflow%3Aci+branch%3Amaster">
      <img alt="Build status" src="https://github.com/parse-community/parse-server/workflows/ci/badge.svg?branch=master">
    </a>
    <a href="https://codecov.io/github/parse-community/parse-server?branch=master"><img alt="Coverage status" src="https://img.shields.io/codecov/c/github/parse-community/parse-server/master.svg"></a>
    <a href="https://www.npmjs.com/package/parse-server"><img alt="npm version" src="https://img.shields.io/npm/v/parse-server.svg?style=flat"></a>
    <a href="https://community.parseplatform.org/"><img alt="Join the conversation" src="https://img.shields.io/discourse/https/community.parseplatform.org/topics.svg"></a>
    <a href="https://snyk.io/test/github/parse-community/parse-server"><img alt="Snyk badge" src="https://snyk.io/test/github/parse-community/parse-server/badge.svg"></a>
    <a href="https://nodejs.org/"><img alt="Node.js 10,12,14,15" src="https://img.shields.io/badge/nodejs-10,_12,_14,_15-green.svg?logo=node.js&style=flat"></a>
    <a href="https://www.mongodb.com/"><img alt="MongoDB 3.6,4.0,4.2,4.4" src="https://img.shields.io/badge/mongodb-3.6,_4.0,_4.2,_4.4-green.svg?logo=mongodb&style=flat"></a>
   <a href="https://www.postgresql.org"> <img alt="PostgreSQL 10,11,12,13" src="https://img.shields.io/badge/postgresql-10,_11,_12,_13-green.svg?logo=postgresql&style=flat"></a>
</p>

<h2 align="center">Our Sponsors</h2>
<p align="center">
    <p align="center">Our backers and sponsors help to ensure the quality and timely development of the Parse Platform.</p>
  <details align="center">
  <summary align="center"><b>🥉 Bronze Sponsors</b></summary>
  <a href="https://opencollective.com/parse-server/sponsor/0/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/0/avatar.svg"></a>
  </details>

</p>
<p align="center">
  <a href="#backers"><img alt="Backers on Open Collective" src="https://opencollective.com/parse-server/tiers/backers/badge.svg" /></a>
  <a href="#sponsors"><img alt="Sponsors on Open Collective" src="https://opencollective.com/parse-server/tiers/sponsors/badge.svg" /></a>
</p>
<br>

Parse Server works with the Express web application framework. It can be added to existing web applications, or run by itself.

The full documentation for Parse Server is available in the [wiki](https://github.com/parse-community/parse-server/wiki). The [Parse Server guide](http://docs.parseplatform.org/parse-server/guide/) is a good place to get started. An [API reference](http://parseplatform.org/parse-server/api/) and [Cloud Code guide](https://docs.parseplatform.org/cloudcode/guide/) are also available. If you're interested in developing for Parse Server, the [Development guide](http://docs.parseplatform.org/parse-server/guide/#development-guide) will help you get set up.

- [Getting Started](#getting-started)
  - [Running Parse Server](#running-parse-server)
    - [Compatibility](#compatibility)
      - [Node.js](#nodejs)
      - [MongoDB](#mongodb)
      - [PostgreSQL](#postgresql)
    - [Locally](#locally)
    - [Docker Container](#docker-container)
    - [Saving an Object](#saving-an-object)
    - [Connect an SDK](#connect-an-sdk)
  - [Running Parse Server elsewhere](#running-parse-server-elsewhere)
    - [Sample Application](#sample-application)
    - [Parse Server + Express](#parse-server--express)
- [Configuration](#configuration)
  - [Basic Options](#basic-options)
  - [Client Key Options](#client-key-options)
  - [Email Verification and Password Reset](#email-verification-and-password-reset)
  - [Custom Routes](#custom-routes)
    - [Example](#example)
    - [Reserved Paths](#reserved-paths)
    - [Parameters](#parameters)
  - [Custom Pages](#custom-pages)
  - [Using Environment Variables](#using-environment-variables)
  - [Available Adapters](#available-adapters)
  - [Configuring File Adapters](#configuring-file-adapters)
  - [Idempotency Enforcement](#idempotency-enforcement)
  - [Localization](#localization)
    - [Pages](#pages)
      - [Localization with Directory Structure](#localization-with-directory-structure)
      - [Localization with JSON Resource](#localization-with-json-resource)
      - [Dynamic placeholders](#dynamic-placeholders)
      - [Reserved Keys](#reserved-keys)
      - [Parameters](#parameters-1)
  - [Logging](#logging)
- [Live Query](#live-query)
- [GraphQL](#graphql)
  - [Running](#running)
    - [Using the CLI](#using-the-cli)
    - [Using Docker](#using-docker)
    - [Using Express.js](#using-expressjs)
  - [Checking the API health](#checking-the-api-health)
  - [Creating your first class](#creating-your-first-class)
  - [Using automatically generated operations](#using-automatically-generated-operations)
  - [Customizing your GraphQL Schema](#customizing-your-graphql-schema)
  - [Learning more](#learning-more)
- [Upgrading to 3.0.0](#upgrading-to-300)
- [Want to ride the bleeding edge?](#want-to-ride-the-bleeding-edge)
- [Contributing](#contributing)
- [Contributors](#contributors)
- [Sponsors](#sponsors)
- [Backers](#backers)

# Getting Started

The fastest and easiest way to get started is to run MongoDB and Parse Server locally.

## Running Parse Server

Before you start make sure you have installed:

- [NodeJS](https://www.npmjs.com/) that includes `npm`
- [MongoDB](https://www.mongodb.com/) or [PostgreSQL](https://www.postgresql.org/)(with [PostGIS](https://postgis.net) 2.2.0 or higher)
- Optionally [Docker](https://www.docker.com/)

### Compatibility

#### Node.js
Parse Server is continuously tested with the most recent releases of Node.js to ensure compatibility. We follow the [Node.js Long Term Support plan](https://github.com/nodejs/Release) and only test against versions that are officially supported and have not reached their end-of-life date.

| Version    | Latest Patch Version | End-of-Life Date | Compatibility      |
|------------|----------------------|------------------|--------------------|
| Node.js 10 | 10.24.0              | April 2021       | ✅ Fully compatible |
| Node.js 12 | 12.21.0              | April 2022       | ✅ Fully compatible |
| Node.js 14 | 14.16.0              | April 2023       | ✅ Fully compatible |
| Node.js 15 | 15.11.0               | June 2021        | ✅ Fully compatible |

#### MongoDB
Parse Server is continuously tested with the most recent releases of MongoDB to ensure compatibility. We follow the [MongoDB support schedule](https://www.mongodb.com/support-policy) and only test against versions that are officially supported and have not reached their end-of-life date.

| Version     | Latest Patch Version | End-of-Life Date | Compatibility      |
|-------------|----------------------|------------------|--------------------|
| MongoDB 3.6 | 3.6.23               | April 2021       | ✅ Fully compatible |
| MongoDB 4.0 | 4.0.23               | January 2022     | ✅ Fully compatible |
| MongoDB 4.2 | 4.2.13               | TBD              | ✅ Fully compatible |
| MongoDB 4.4 | 4.4.4                | TBD              | ✅ Fully compatible |
  
#### PostgreSQL
Parse Server is continuously tested with the most recent releases of PostgreSQL and PostGIS to ensure compatibility. We follow the [PostGIS docker tags](https://registry.hub.docker.com/r/postgis/postgis/tags?page=1&ordering=last_updated) and only test against versions that are officially supported and have not reached their end-of-life date.

| Version       | PostGIS Version | End-of-Life Date | Compatibility      |
|---------------|-----------------|------------------|--------------------|
| Postgres 10.x | 3.0.x, 3.1.x    | November 2022    | ✅ Fully compatible |
| Postgres 11.x | 3.0.x, 3.1.x    | November 2023    | ✅ Fully compatible |
| Postgres 12.x | 3.0.x, 3.1.x    | November 2024    | ✅ Fully compatible |
| Postgres 13.x | 3.0.x, 3.1.x    | November 2025    | ✅ Fully compatible |

### Locally
```bash
$ npm install -g parse-server mongodb-runner
$ mongodb-runner start
$ parse-server --appId APPLICATION_ID --masterKey MASTER_KEY --databaseURI mongodb://localhost/test
```
***Note:*** *If installation with* `-g` *fails due to permission problems* (`npm ERR! code 'EACCES'`), *please refer to [this link](https://docs.npmjs.com/getting-started/fixing-npm-permissions).*


### Docker Container

```bash
$ git clone https://github.com/parse-community/parse-server
$ cd parse-server
$ docker build --tag parse-server .
$ docker run --name my-mongo -d mongo
```

#### Running the Parse Server Image <!-- omit in toc -->

```bash
$ docker run --name my-parse-server -v config-vol:/parse-server/config -p 1337:1337 --link my-mongo:mongo -d parse-server --appId APPLICATION_ID --masterKey MASTER_KEY --databaseURI mongodb://mongo/test
```

***Note:*** *If you want to use [Cloud Code](https://docs.parseplatform.org/cloudcode/guide/), add `-v cloud-code-vol:/parse-server/cloud --cloud /parse-server/cloud/main.js` to the command above. Make sure `main.js` is in the `cloud-code-vol` directory before starting Parse Server.*

You can use any arbitrary string as your application id and master key. These will be used by your clients to authenticate with the Parse Server.

That's it! You are now running a standalone version of Parse Server on your machine.

**Using a remote MongoDB?** Pass the  `--databaseURI DATABASE_URI` parameter when starting `parse-server`. Learn more about configuring Parse Server [here](#configuration). For a full list of available options, run `parse-server --help`.

### Saving an Object

Now that you're running Parse Server, it is time to save your first object. We'll use the [REST API](http://docs.parseplatform.org/rest/guide), but you can easily do the same using any of the [Parse SDKs](http://parseplatform.org/#sdks). Run the following:

```bash
$ curl -X POST \
-H "X-Parse-Application-Id: APPLICATION_ID" \
-H "Content-Type: application/json" \
-d '{"score":1337,"playerName":"Sean Plott","cheatMode":false}' \
http://localhost:1337/parse/classes/GameScore
```

You should get a response similar to this:

```js
{
  "objectId": "2ntvSpRGIK",
  "createdAt": "2016-03-11T23:51:48.050Z"
}
```

You can now retrieve this object directly (make sure to replace `2ntvSpRGIK` with the actual `objectId` you received when the object was created):

```bash
$ curl -X GET \
  -H "X-Parse-Application-Id: APPLICATION_ID" \
  http://localhost:1337/parse/classes/GameScore/2ntvSpRGIK
```
```json
// Response
{
  "objectId": "2ntvSpRGIK",
  "score": 1337,
  "playerName": "Sean Plott",
  "cheatMode": false,
  "updatedAt": "2016-03-11T23:51:48.050Z",
  "createdAt": "2016-03-11T23:51:48.050Z"
}
```

Keeping tracks of individual object ids is not ideal, however. In most cases you will want to run a query over the collection, like so:

```bash
$ curl -X GET \
  -H "X-Parse-Application-Id: APPLICATION_ID" \
  http://localhost:1337/parse/classes/GameScore
```
```json
// The response will provide all the matching objects within the `results` array:
{
  "results": [
    {
      "objectId": "2ntvSpRGIK",
      "score": 1337,
      "playerName": "Sean Plott",
      "cheatMode": false,
      "updatedAt": "2016-03-11T23:51:48.050Z",
      "createdAt": "2016-03-11T23:51:48.050Z"
    }
  ]
}

```

To learn more about using saving and querying objects on Parse Server, check out the [Parse documentation](http://docs.parseplatform.org).

### Connect an SDK

Parse provides SDKs for all the major platforms. Refer to the Parse Server guide to [learn how to connect your app to Parse Server](https://docs.parseplatform.org/parse-server/guide/#using-parse-sdks-with-parse-server).

## Running Parse Server elsewhere

Once you have a better understanding of how the project works, please refer to the [Parse Server wiki](https://github.com/parse-community/parse-server/wiki) for in-depth guides to deploy Parse Server to major infrastructure providers. Read on to learn more about additional ways of running Parse Server.

### Sample Application

We have provided a basic [Node.js application](https://github.com/parse-community/parse-server-example) that uses the Parse Server module on Express and can be easily deployed to various infrastructure providers:

* [Heroku and mLab](https://devcenter.heroku.com/articles/deploying-a-parse-server-to-heroku)
* [AWS and Elastic Beanstalk](http://mobile.awsblog.com/post/TxCD57GZLM2JR/How-to-set-up-Parse-Server-on-AWS-using-AWS-Elastic-Beanstalk)
* [Google App Engine](https://medium.com/@justinbeckwith/deploying-parse-server-to-google-app-engine-6bc0b7451d50)
* [Microsoft Azure](https://azure.microsoft.com/en-us/blog/azure-welcomes-parse-developers/)
* [SashiDo](https://blog.sashido.io/tag/migration/)
* [Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-run-parse-server-on-ubuntu-14-04)
* [Pivotal Web Services](https://github.com/cf-platform-eng/pws-parse-server)
* [Back4app](http://blog.back4app.com/2016/03/01/quick-wizard-migration/)
* [Glitch](https://glitch.com/edit/#!/parse-server)
* [Flynn](https://flynn.io/blog/parse-apps-on-flynn)

### Parse Server + Express

You can also create an instance of Parse Server, and mount it on a new or existing Express website:

```js
var express = require('express');
var ParseServer = require('parse-server').ParseServer;
var app = express();

var api = new ParseServer({
  databaseURI: 'mongodb://localhost:27017/dev', // Connection string for your MongoDB database
  cloud: './cloud/main.js', // Path to your Cloud Code
  appId: 'myAppId',
  masterKey: 'myMasterKey', // Keep this key secret!
  fileKey: 'optionalFileKey',
  serverURL: 'http://localhost:1337/parse' // Don't forget to change to https if needed
});

// Serve the Parse API on the /parse URL prefix
app.use('/parse', api);

app.listen(1337, function() {
  console.log('parse-server-example running on port 1337.');
});
```

For a full list of available options, run `parse-server --help` or take a look at [Parse Server Configurations](http://parseplatform.org/parse-server/api/master/ParseServerOptions.html).

# Configuration

Parse Server can be configured using the following options. You may pass these as parameters when running a standalone `parse-server`, or by loading a configuration file in JSON format using `parse-server path/to/configuration.json`. If you're using Parse Server on Express, you may also pass these to the `ParseServer` object as options.

For the full list of available options, run `parse-server --help` or take a look at [Parse Server Configurations](http://parseplatform.org/parse-server/api/master/ParseServerOptions.html).

## Basic Options

* `appId` **(required)** - The application id to host with this server instance. You can use any arbitrary string. For migrated apps, this should match your hosted Parse app.
* `masterKey` **(required)** - The master key to use for overriding ACL security.  You can use any arbitrary string. Keep it secret! For migrated apps, this should match your hosted Parse app.
* `databaseURI` **(required)** - The connection string for your database, i.e. `mongodb://user:pass@host.com/dbname`. Be sure to [URL encode your password](https://app.zencoder.com/docs/guides/getting-started/special-characters-in-usernames-and-passwords) if your password has special characters.
* `port` - The default port is 1337, specify this parameter to use a different port.
* `serverURL` - URL to your Parse Server (don't forget to specify http:// or https://). This URL will be used when making requests to Parse Server from Cloud Code.
* `cloud` - The absolute path to your cloud code `main.js` file.
* `push` - Configuration options for APNS and GCM push. See the [Push Notifications quick start](http://docs.parseplatform.org/parse-server/guide/#push-notifications_push-notifications-quick-start).

## Client Key Options

The client keys used with Parse are no longer necessary with Parse Server. If you wish to still require them, perhaps to be able to refuse access to older clients, you can set the keys at initialization time. Setting any of these keys will require all requests to provide one of the configured keys.

* `clientKey`
* `javascriptKey`
* `restAPIKey`
* `dotNetKey`

## Email Verification and Password Reset

Verifying user email addresses and enabling password reset via email requires an email adapter. As part of the `parse-server` package we provide an adapter for sending email through Mailgun. To use it, sign up for Mailgun, and add this to your initialization code:

```js
var server = ParseServer({
  ...otherOptions,
  // Enable email verification
  verifyUserEmails: true,

  // if `verifyUserEmails` is `true` and
  //     if `emailVerifyTokenValidityDuration` is `undefined` then
  //        email verify token never expires
  //     else
  //        email verify token expires after `emailVerifyTokenValidityDuration`
  //
  // `emailVerifyTokenValidityDuration` defaults to `undefined`
  //
  // email verify token below expires in 2 hours (= 2 * 60 * 60 == 7200 seconds)
  emailVerifyTokenValidityDuration: 2 * 60 * 60, // in seconds (2 hours = 7200 seconds)

  // set preventLoginWithUnverifiedEmail to false to allow user to login without verifying their email
  // set preventLoginWithUnverifiedEmail to true to prevent user from login if their email is not verified
  preventLoginWithUnverifiedEmail: false, // defaults to false

  // The public URL of your app.
  // This will appear in the link that is used to verify email addresses and reset passwords.
  // Set the mount path as it is in serverURL
  publicServerURL: 'https://example.com/parse',
  // Your apps name. This will appear in the subject and body of the emails that are sent.
  appName: 'Parse App',
  // The email adapter
  emailAdapter: {
    module: '@parse/simple-mailgun-adapter',
    options: {
      // The address that your emails come from
      fromAddress: 'parse@example.com',
      // Your domain from mailgun.com
      domain: 'example.com',
      // Your API key from mailgun.com
      apiKey: 'key-mykey',
    }
  },

  // account lockout policy setting (OPTIONAL) - defaults to undefined
  // if the account lockout policy is set and there are more than `threshold` number of failed login attempts then the `login` api call returns error code `Parse.Error.OBJECT_NOT_FOUND` with error message `Your account is locked due to multiple failed login attempts. Please try again after <duration> minute(s)`. After `duration` minutes of no login attempts, the application will allow the user to try login again.
  accountLockout: {
    duration: 5, // duration policy setting determines the number of minutes that a locked-out account remains locked out before automatically becoming unlocked. Set it to a value greater than 0 and less than 100000.
    threshold: 3, // threshold policy setting determines the number of failed sign-in attempts that will cause a user account to be locked. Set it to an integer value greater than 0 and less than 1000.
    unlockOnPasswordReset: true, // Is true if the account lock should be removed after a successful password reset. Default: false.
}
  },
  // optional settings to enforce password policies
  passwordPolicy: {
    // Two optional settings to enforce strong passwords. Either one or both can be specified.
    // If both are specified, both checks must pass to accept the password
    // 1. a RegExp object or a regex string representing the pattern to enforce
    validatorPattern: /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.{8,})/, // enforce password with at least 8 char with at least 1 lower case, 1 upper case and 1 digit
    // 2. a callback function to be invoked to validate the password
    validatorCallback: (password) => { return validatePassword(password) },
    validationError: 'Password must contain at least 1 digit.' // optional error message to be sent instead of the default "Password does not meet the Password Policy requirements." message.
    doNotAllowUsername: true, // optional setting to disallow username in passwords
    maxPasswordAge: 90, // optional setting in days for password expiry. Login fails if user does not reset the password within this period after signup/last reset.
    maxPasswordHistory: 5, // optional setting to prevent reuse of previous n passwords. Maximum value that can be specified is 20. Not specifying it or specifying 0 will not enforce history.
    //optional setting to set a validity duration for password reset links (in seconds)
    resetTokenValidityDuration: 24*60*60, // expire after 24 hours
  }
});
```

You can also use other email adapters contributed by the community such as:
- [parse-smtp-template (Multi Language and Multi Template)](https://www.npmjs.com/package/parse-smtp-template)
- [parse-server-postmark-adapter](https://www.npmjs.com/package/parse-server-postmark-adapter)
- [parse-server-sendgrid-adapter](https://www.npmjs.com/package/parse-server-sendgrid-adapter)
- [parse-server-mandrill-adapter](https://www.npmjs.com/package/parse-server-mandrill-adapter)
- [parse-server-simple-ses-adapter](https://www.npmjs.com/package/parse-server-simple-ses-adapter)
- [parse-server-mailgun-adapter-template](https://www.npmjs.com/package/parse-server-mailgun-adapter-template)
- [parse-server-sendinblue-adapter](https://www.npmjs.com/package/parse-server-sendinblue-adapter)
- [parse-server-mailjet-adapter](https://www.npmjs.com/package/parse-server-mailjet-adapter)
- [simple-parse-smtp-adapter](https://www.npmjs.com/package/simple-parse-smtp-adapter)
- [parse-server-generic-email-adapter](https://www.npmjs.com/package/parse-server-generic-email-adapter)
- [parse-server-api-mail-adapter](https://www.npmjs.com/package/parse-server-api-mail-adapter)

## Custom Routes
**Caution, this is an experimental feature that may not be appropriate for production.**

Custom routes allow to build user flows with webpages, similar to the existing password reset and email verification features. Custom routes are defined with the `pages` option in the Parse Server configuration:

### Example

```js
const api = new ParseServer({
  ...otherOptions,

  pages: {
    enableRouter: true, // Enables the experimental feature; required for custom routes
    customRoutes: [{
      method: 'GET',
      path: 'custom_route',
      handler: async request => {
        // custom logic
        // ...
        // then, depending on the outcome, return a HTML file as response
        return { file: 'custom_page.html' };
      }
    }]
  }
}
```

The above route can be invoked by sending a `GET` request to:
`https://[parseServerPublicUrl]/[parseMount]/[pagesEndpoint]/[appId]/[customRoute]`
 
The `handler` receives the `request` and returns a `custom_page.html` webpage from the `pages.pagesPath` directory as response. The advantage of building a custom route this way is that it automatically makes use of Parse Server's built-in capabilities, such as [page localization](#pages) and [dynamic placeholders](#dynamic-placeholders).

### Reserved Paths
The following paths are already used by Parse Server's built-in features and are therefore not available for custom routes. Custom routes with an identical combination of `path` and `method` are ignored.

| Path                        | HTTP Method | Feature            |
|-----------------------------|-------------|--------------------|
| `verify_email`              | `GET`       | email verification |
| `resend_verification_email` | `POST`      | email verification |
| `choose_password`           | `GET`       | password reset     |
| `request_password_reset`    | `GET`       | password reset     |
| `request_password_reset`    | `POST`      | password reset     |

### Parameters

| Parameter                    | Optional | Type            | Default value | Example values        | Environment variable               | Description                                                                                                                                                                                                                                                  |
|------------------------------|----------|-----------------|---------------|-----------------------|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `pages`                      | yes      | `Object`        | `undefined`   | -                     | `PARSE_SERVER_PAGES`               | The options for pages such as password reset and email verification.                                                                                                                                                                                         |
| `pages.enableRouter`         | yes      | `Boolean`       | `false`       | -                     | `PARSE_SERVER_PAGES_ENABLE_ROUTER` | Is `true` if the pages router should be enabled; this is required for any of the pages options to take effect. **Caution, this is an experimental feature that may not be appropriate for production.**                                                      |
| `pages.customRoutes`         | yes      | `Array`         | `[]`          | -                     | `PARSE_SERVER_PAGES_CUSTOM_ROUTES` | The custom routes. The routes are added in the order they are defined here, which has to be considered since requests traverse routes in an ordered manner. Custom routes are traversed after build-in routes such as password reset and email verification. |
| `pages.customRoutes.method`  |          | `String`        | -             | `GET`, `POST`         | -                                  | The HTTP method of the custom route.                                                                                                                                                                                                                         |
| `pages.customRoutes.path`    |          | `String`        | -             | `custom_page`         | -                                  | The path of the custom route. Note that the same path can used if the `method` is different, for example a path `custom_page` can have two routes, a `GET` and `POST` route, which will be invoked depending on the HTTP request method.                     |
| `pages.customRoutes.handler` |          | `AsyncFunction` | -             | `async () => { ... }` | -                                  | The route handler that is invoked when the route matches the HTTP request. If the handler does not return a page, the request is answered with a 404 `Not found.` response.                                                                                  |

## Custom Pages

It’s possible to change the default pages of the app and redirect the user to another path or domain.

```js
var server = ParseServer({
  ...otherOptions,

  customPages: {
    passwordResetSuccess: "http://yourapp.com/passwordResetSuccess",
    verifyEmailSuccess: "http://yourapp.com/verifyEmailSuccess",
    parseFrameURL: "http://yourapp.com/parseFrameURL",
    linkSendSuccess: "http://yourapp.com/linkSendSuccess",
    linkSendFail: "http://yourapp.com/linkSendFail",
    invalidLink: "http://yourapp.com/invalidLink",
    invalidVerificationLink: "http://yourapp.com/invalidVerificationLink",
    choosePassword: "http://yourapp.com/choosePassword"
  }
})
```

## Using Environment Variables

You may configure the Parse Server using environment variables:

```bash
PORT
PARSE_SERVER_APPLICATION_ID
PARSE_SERVER_MASTER_KEY
PARSE_SERVER_DATABASE_URI
PARSE_SERVER_URL
PARSE_SERVER_CLOUD
```

The default port is 1337, to use a different port set the PORT environment variable:

```bash
$ PORT=8080 parse-server --appId APPLICATION_ID --masterKey MASTER_KEY
```

For the full list of configurable environment variables, run `parse-server --help` or take a look at [Parse Server Configuration](https://github.com/parse-community/parse-server/blob/master/src/Options/Definitions.js).

## Available Adapters

All official adapters are distributed as scoped packages on [npm (@parse)](https://www.npmjs.com/search?q=scope%3Aparse).

Some well maintained adapters are also available on the [Parse Server Modules](https://github.com/parse-server-modules) organization.

You can also find more adapters maintained by the community by searching on [npm](https://www.npmjs.com/search?q=parse-server%20adapter&page=1&ranking=optimal).

## Configuring File Adapters

Parse Server allows developers to choose from several options when hosting files:

* `GridFSBucketAdapter`, which is backed by MongoDB;
* `S3Adapter`, which is backed by [Amazon S3](https://aws.amazon.com/s3/); or
* `GCSAdapter`, which is backed by [Google Cloud Storage](https://cloud.google.com/storage/)

`GridFSBucketAdapter` is used by default and requires no setup, but if you're interested in using S3 or Google Cloud Storage, additional configuration information is available in the [Parse Server guide](http://docs.parseplatform.org/parse-server/guide/#configuring-file-adapters).

## Idempotency Enforcement
 
**Caution, this is an experimental feature that may not be appropriate for production.**

This feature deduplicates identical requests that are received by Parse Server multiple times, typically due to network issues or network adapter access restrictions on mobile operating systems.

Identical requests are identified by their request header `X-Parse-Request-Id`. Therefore a client request has to include this header for deduplication to be applied. Requests that do not contain this header cannot be deduplicated and are processed normally by Parse Server. This means rolling out this feature to clients is seamless as Parse Server still processes requests without this header when this feature is enabled.

> This feature needs to be enabled on the client side to send the header and on the server to process the header. Refer to the specific Parse SDK docs to see whether the feature is supported yet.

Deduplication is only done for object creation and update (`POST` and `PUT` requests). Deduplication is not done for object finding and deletion (`GET` and `DELETE` requests), as these operations are already idempotent by definition.

### Configuration example <!-- omit in toc -->
```
let api = new ParseServer({
    idempotencyOptions: {
        paths: [".*"],       // enforce for all requests
        ttl: 120             // keep request IDs for 120s
    }
}
```
### Parameters <!-- omit in toc -->

| Parameter                  | Optional | Type            | Default value | Example values                                                                                                                                                                                                                                                              | Environment variable                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------|----------|-----------------|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `idempotencyOptions`       | yes      | `Object`        | `undefined`   |                                                                                                                                                                                                                                                                             | PARSE_SERVER_EXPERIMENTAL_IDEMPOTENCY_OPTIONS | Setting this enables idempotency enforcement for the specified paths.                                                                                                                                                                                                                                                                                                                                                                                |
| `idempotencyOptions.paths` | yes      | `Array<String>` | `[]`          | `.*` (all paths, includes the examples below), <br>`functions/.*` (all functions), <br>`jobs/.*` (all jobs), <br>`classes/.*` (all classes), <br>`functions/.*` (all functions), <br>`users` (user creation / update), <br>`installations` (installation creation / update) | PARSE_SERVER_EXPERIMENTAL_IDEMPOTENCY_PATHS   | An array of path patterns that have to match the request path for request deduplication to be enabled. The mount path must not be included, for example to match the request path `/parse/functions/myFunction` specify the path pattern `functions/myFunction`. A trailing slash of the request path is ignored, for example the path pattern `functions/myFunction` matches both `/parse/functions/myFunction` and `/parse/functions/myFunction/`. |
| `idempotencyOptions.ttl`   | yes      | `Integer`       | `300`         | `60` (60 seconds)                                                                                                                                                                                                                                                           | PARSE_SERVER_EXPERIMENTAL_IDEMPOTENCY_TTL     | The duration in seconds after which a request record is discarded from the database. Duplicate requests due to network issues can be expected to arrive within milliseconds up to several seconds. This value must be greater than `0`.                                                                                                                                                                                                              |

### Notes <!-- omit in toc -->

- This feature is currently only available for MongoDB and not for Postgres.

## Localization

### Pages
**Caution, this is an experimental feature that may not be appropriate for production.**

Custom pages as well as feature pages (e.g. password reset, email verification) can be localized with the `pages` option in the Parse Server configuration:

```js
const api = new ParseServer({
  ...otherOptions,

  pages: {
    enableRouter: true, // Enables the experimental feature; required for localization
    enableLocalization: true,
  }
}
```

Localization is achieved by matching a request-supplied `locale` parameter with localized page content. The locale can be supplied in either the request query, body or header with the following keys:
- query: `locale`
- body: `locale`
- header: `x-parse-page-param-locale`

For example, a password reset link with the locale parameter in the query could look like this:
```
http://example.com/parse/apps/[appId]/request_password_reset?token=[token]&username=[username]&locale=de-AT
```

- Localization is only available for pages in the pages directory as set with `pages.pagesPath`.
- Localization for feature pages (e.g. password reset, email verification) is disabled if `pages.customUrls` are set, even if the custom URLs point to the pages within the pages path.
- Only `.html` files are considered for localization when localizing custom pages.

Pages can be localized in two ways:

#### Localization with Directory Structure

Pages are localized by using the corresponding file in the directory structure where the files are placed in subdirectories named after the locale or language. The file in the base directory is the default file.

**Example Directory Structure:**
```js
root/
├── public/                  // pages base path
│   ├── example.html         // default file
│   └── de/                  // de language folder
│   │   └── example.html     // de localized file
│   └── de-AT/               // de-AT locale folder
│   │   └── example.html     // de-AT localized file
```

Files are matched with the locale in the following order:
1. Locale match, e.g. locale `de-AT` matches file in folder `de-AT`.
1. Language match, e.g. locale `de-CH` matches file in folder `de`.
1. Default; file in base folder is returned.

**Configuration Example:**
```js
const api = new ParseServer({
  ...otherOptions,

  pages: {
    enableRouter: true, // Enables the experimental feature; required for localization
    enableLocalization: true,
    customUrls: {
      passwordReset: 'https://example.com/page.html'
    }
  }
}
```

Pros:
- All files are complete in their content and can be easily opened and previewed by viewing the file in a browser.

Cons:
- In most cases, a localized page differs only slightly from the default page, which could cause a lot of duplicate code that is difficult to maintain.

#### Localization with JSON Resource

Pages are localized by adding placeholders in the HTML files and providing a JSON resource that contains the translations to fill into the placeholders.

**Example Directory Structure:**
```js
root/
├── public/                  // pages base path
│   ├── example.html         // the page containing placeholders
├── private/                 // folder outside of public scope
│   └── translations.json    // JSON resource file
```

The JSON resource file loosely follows the [i18next](https://github.com/i18next/i18next) syntax, which is a syntax that is often supported by translation platforms, making it easy to manage translations, exporting them for use in Parse Server, and even to automate this workflow.

**Example JSON Content:**
```json
{
  "en": {               // resource for language `en` (English)
    "translation": {
      "greeting": "Hello!"
    }
  },
  "de": {               // resource for language `de` (German)
    "translation": {
      "greeting": "Hallo!"
    }
  }
  "de-AT": {            // resource for locale `de-AT` (Austrian German)
    "translation": {
      "greeting": "Servus!"
    }
  }
}
```

**Configuration Example:**
```js
const api = new ParseServer({
  ...otherOptions,

  pages: {
    enableRouter: true, // Enables the experimental feature; required for localization
    enableLocalization: true,
    localizationJsonPath: './private/localization.json',
    localizationFallbackLocale: 'en'
  }
}
```

Pros:
- There is only one HTML file to maintain that contains the placeholders that are filled with the translations according to the locale.

Cons:
- Files cannot be easily previewed by viewing the file in a browser because the content contains only placeholders and even HTML or CSS changes may be dynamically applied, e.g. when a localization requires a Right-To-Left layout direction.
- Style and other fundamental layout changes may be more difficult to apply.

#### Dynamic placeholders

In addition to feature related default parameters such as `appId` and the translations provided via JSON resource, it is possible to define custom dynamic placeholders as part of the router configuration. This works independently of localization and, also if `enableLocalization` is disabled.

**Configuration Example:**
```js
const api = new ParseServer({
  ...otherOptions,

  pages: {
    enableRouter: true, // Enables the experimental feature; required for localization
    placeholders: {
      exampleKey: 'exampleValue'
    }
  }
}
```
The placeholders can also be provided as function or as async function, with the `locale` and other feature related parameters passed through, to allow for dynamic placeholder values:

```js
const api = new ParseServer({
  ...otherOptions,

  pages: {
    enableRouter: true, // Enables the experimental feature; required for localization
    placeholders: async (params) => {
      const value = await doSomething(params.locale);
      return {
        exampleKey: value
      };
    }
  }
}
```

#### Reserved Keys

The following parameter and placeholder keys are reserved because they are used related to features such as password reset or email verification. They should not be used as translation keys in the JSON resource or as manually defined placeholder keys in the configuration: `appId`, `appName`, `email`, `error`, `locale`, `publicServerUrl`, `token`, `username`.

#### Parameters

| Parameter                                       | Optional | Type                                  | Default value                          | Example values                                       | Environment variable                                            | Description                                                                                                                                                                                                   |
|-------------------------------------------------|----------|---------------------------------------|----------------------------------------|------------------------------------------------------|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `pages`                                         | yes      | `Object`                              | `undefined`                            | -                                                    | `PARSE_SERVER_PAGES`                                            | The options for pages such as password reset and email verification.                                                                                                                                          |
| `pages.enableRouter`                            | yes      | `Boolean`                             | `false`                                | -                                                    | `PARSE_SERVER_PAGES_ENABLE_ROUTER`                              | Is `true` if the pages router should be enabled; this is required for any of the pages options to take effect. **Caution, this is an experimental feature that may not be appropriate for production.**       |
| `pages.enableLocalization`                      | yes      | `Boolean`                             | `false`                                | -                                                    | `PARSE_SERVER_PAGES_ENABLE_LOCALIZATION`                        | Is true if pages should be localized; this has no effect on custom page redirects.                                                                                                                            |
| `pages.localizationJsonPath`                    | yes      | `String`                              | `undefined`                            | `./private/translations.json`                        | `PARSE_SERVER_PAGES_LOCALIZATION_JSON_PATH`                     | The path to the JSON file for localization; the translations will be used to fill template placeholders according to the locale.                                                                              |
| `pages.localizationFallbackLocale`              | yes      | `String`                              | `en`                                   | `en`, `en-GB`, `default`                             | `PARSE_SERVER_PAGES_LOCALIZATION_FALLBACK_LOCALE`               | The fallback locale for localization if no matching translation is provided for the given locale. This is only relevant when providing translation resources via JSON file.                                   |
| `pages.placeholders`                            | yes      | `Object`, `Function`, `AsyncFunction` | `undefined`                            | `{ exampleKey: 'exampleValue' }`                     | `PARSE_SERVER_PAGES_PLACEHOLDERS`                               | The placeholder keys and values which will be filled in pages; this can be a simple object or a callback function.                                                                                            |
| `pages.forceRedirect`                           | yes      | `Boolean`                             | `false`                                | -                                                    | `PARSE_SERVER_PAGES_FORCE_REDIRECT`                             | Is `true` if responses should always be redirects and never content, `false` if the response type should depend on the request type (`GET` request -> content response; `POST` request -> redirect response). |
| `pages.pagesPath`                               | yes      | `String`                              | `./public`                             | `./files/pages`, `../../pages`                       | `PARSE_SERVER_PAGES_PAGES_PATH`                                 | The path to the pages directory; this also defines where the static endpoint `/apps` points to.                                                                                                               |
| `pages.pagesEndpoint`                           | yes      | `String`                              | `apps`                                 | -                                                    | `PARSE_SERVER_PAGES_PAGES_ENDPOINT`                             | The API endpoint for the pages.                                                                                                                                                                               |
| `pages.customUrls`                              | yes      | `Object`                              | `{}`                                   | `{ passwordReset: 'https://example.com/page.html' }` | `PARSE_SERVER_PAGES_CUSTOM_URLS`                                | The URLs to the custom pages                                                                                                                                                                                  |
| `pages.customUrls.passwordReset`                | yes      | `String`                              | `password_reset.html`                  | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_PASSWORD_RESET`                  | The URL to the custom page for password reset.                                                                                                                                                                |
| `pages.customUrls.passwordResetSuccess`         | yes      | `String`                              | `password_reset_success.html`          | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_PASSWORD_RESET_SUCCESS`          | The URL to the custom page for password reset -> success.                                                                                                                                                     |
| `pages.customUrls.passwordResetLinkInvalid`     | yes      | `String`                              | `password_reset_link_invalid.html`     | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_PASSWORD_RESET_LINK_INVALID`     | The URL to the custom page for password reset -> link invalid.                                                                                                                                                |
| `pages.customUrls.emailVerificationSuccess`     | yes      | `String`                              | `email_verification_success.html`      | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_EMAIL_VERIFICATION_SUCCESS`      | The URL to the custom page for email verification -> success.                                                                                                                                                 |
| `pages.customUrls.emailVerificationSendFail`    | yes      | `String`                              | `email_verification_send_fail.html`    | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_EMAIL_VERIFICATION_SEND_FAIL`    | The URL to the custom page for email verification -> link send fail.                                                                                                                                          |
| `pages.customUrls.emailVerificationSendSuccess` | yes      | `String`                              | `email_verification_send_success.html` | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_EMAIL_VERIFICATION_SEND_SUCCESS` | The URL to the custom page for email verification -> resend link -> success.                                                                                                                                  |
| `pages.customUrls.emailVerificationLinkInvalid` | yes      | `String`                              | `email_verification_link_invalid.html` | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_EMAIL_VERIFICATION_LINK_INVALID` | The URL to the custom page for email verification -> link invalid.                                                                                                                                            |
| `pages.customUrls.emailVerificationLinkExpired` | yes      | `String`                              | `email_verification_link_expired.html` | -                                                    | `PARSE_SERVER_PAGES_CUSTOM_URL_EMAIL_VERIFICATION_LINK_EXPIRED` | The URL to the custom page for email verification -> link expired.                                                                                                                                            |

### Notes <!-- omit in toc -->

- In combination with the [Parse Server API Mail Adapter](https://www.npmjs.com/package/parse-server-api-mail-adapter) Parse Server provides a fully localized flow (emails -> pages) for the user. The email adapter sends a localized email and adds a locale parameter to the password reset or email verification link, which is then used to respond with localized pages.

## Logging

Parse Server will, by default, log:
* to the console
* daily rotating files as new line delimited JSON

Logs are also viewable in Parse Dashboard.

**Want to log each request and response?** Set the `VERBOSE` environment variable when starting `parse-server`. Usage :-  `VERBOSE='1' parse-server --appId APPLICATION_ID --masterKey MASTER_KEY`

**Want logs to be placed in a different folder?** Pass the `PARSE_SERVER_LOGS_FOLDER` environment variable when starting `parse-server`. Usage :-  `PARSE_SERVER_LOGS_FOLDER='<path-to-logs-folder>' parse-server --appId APPLICATION_ID --masterKey MASTER_KEY`

**Want to log specific levels?** Pass the `logLevel` parameter when starting `parse-server`. Usage :-  `parse-server --appId APPLICATION_ID --masterKey MASTER_KEY --logLevel LOG_LEVEL`

**Want new line delimited JSON error logs (for consumption by CloudWatch, Google Cloud Logging, etc)?** Pass the `JSON_LOGS` environment variable when starting `parse-server`. Usage :-  `JSON_LOGS='1' parse-server --appId APPLICATION_ID --masterKey MASTER_KEY`

# Live Query

Live queries are meant to be used in real-time reactive applications, where just using the traditional query paradigm could cause several problems, like increased response time and high network and server usage. Live queries should be used in cases where you need to continuously update a page with fresh data coming from the database, which often happens in (but is not limited to) online games, messaging clients and shared to-do lists.

Take a look at [Live Query Guide](https://docs.parseplatform.org/parse-server/guide/#live-queries), [Live Query Server Setup Guide](https://docs.parseplatform.org/parse-server/guide/#scalability) and [Live Query Protocol Specification](https://github.com/parse-community/parse-server/wiki/Parse-LiveQuery-Protocol-Specification). You can setup a standalone server or multiple instances for scalability (recommended).

# GraphQL

[GraphQL](https://graphql.org/), developed by Facebook, is an open-source data query and manipulation language for APIs. In addition to the traditional REST API, Parse Server automatically generates a GraphQL API based on your current application schema. Parse Server also allows you to define your custom GraphQL queries and mutations, whose resolvers can be bound to your cloud code functions.

## Running

### Using the CLI

The easiest way to run the Parse GraphQL API is through the CLI:

```bash
$ npm install -g parse-server mongodb-runner
$ mongodb-runner start
$ parse-server --appId APPLICATION_ID --masterKey MASTER_KEY --databaseURI mongodb://localhost/test --publicServerURL http://localhost:1337/parse --mountGraphQL --mountPlayground
```

After starting the server, you can visit http://localhost:1337/playground in your browser to start playing with your GraphQL API.

***Note:*** Do ***NOT*** use --mountPlayground option in production. [Parse Dashboard](https://github.com/parse-community/parse-dashboard) has a built-in GraphQL Playground and it is the recommended option for production apps.

### Using Docker

You can also run the Parse GraphQL API inside a Docker container:

```bash
$ git clone https://github.com/parse-community/parse-server
$ cd parse-server
$ docker build --tag parse-server .
$ docker run --name my-mongo -d mongo
```

#### Running the Parse Server Image <!-- omit in toc -->

```bash
$ docker run --name my-parse-server --link my-mongo:mongo -v config-vol:/parse-server/config -p 1337:1337 -d parse-server --appId APPLICATION_ID --masterKey MASTER_KEY --databaseURI mongodb://mongo/test --publicServerURL http://localhost:1337/parse --mountGraphQL --mountPlayground
```

***Note:*** *If you want to use [Cloud Code](https://docs.parseplatform.org/cloudcode/guide/), add `-v cloud-code-vol:/parse-server/cloud --cloud /parse-server/cloud/main.js` to the command above. Make sure `main.js` is in the `cloud-code-vol` directory before starting Parse Server.*

After starting the server, you can visit http://localhost:1337/playground in your browser to start playing with your GraphQL API.

***Note:*** Do ***NOT*** use --mountPlayground option in production. [Parse Dashboard](https://github.com/parse-community/parse-dashboard) has a built-in GraphQL Playground and it is the recommended option for production apps.

### Using Express.js

You can also mount the GraphQL API in an Express.js application together with the REST API or solo. You first need to create a new project and install the required dependencies:

```bash
$ mkdir my-app
$ cd my-app
$ npm install parse-server express --save
```

Then, create an `index.js` file with the following content:

```js
const express = require('express');
const { default: ParseServer, ParseGraphQLServer } = require('parse-server');

const app = express();

const parseServer = new ParseServer({
  databaseURI: 'mongodb://localhost:27017/test',
  appId: 'APPLICATION_ID',
  masterKey: 'MASTER_KEY',
  serverURL: 'http://localhost:1337/parse',
  publicServerURL: 'http://localhost:1337/parse'
});

const parseGraphQLServer = new ParseGraphQLServer(
  parseServer,
  {
    graphQLPath: '/graphql',
    playgroundPath: '/playground'
  }
);

app.use('/parse', parseServer.app); // (Optional) Mounts the REST API
parseGraphQLServer.applyGraphQL(app); // Mounts the GraphQL API
parseGraphQLServer.applyPlayground(app); // (Optional) Mounts the GraphQL Playground - do NOT use in Production

app.listen(1337, function() {
  console.log('REST API running on http://localhost:1337/parse');
  console.log('GraphQL API running on http://localhost:1337/graphql');
  console.log('GraphQL Playground running on http://localhost:1337/playground');
});
```

And finally start your app:

```bash
$ npx mongodb-runner start
$ node index.js
```

After starting the app, you can visit http://localhost:1337/playground in your browser to start playing with your GraphQL API.

***Note:*** Do ***NOT*** mount the GraphQL Playground in production. [Parse Dashboard](https://github.com/parse-community/parse-dashboard) has a built-in GraphQL Playground and it is the recommended option for production apps.

## Checking the API health

Run the following:

```graphql
query Health {
  health
}
```

You should receive the following response:

```json
{
  "data": {
    "health": true
  }
}
```

## Creating your first class

Since your application does not have any schema yet, you can use the `createClass` mutation to create your first class. Run the following:

```graphql
mutation CreateClass {
  createClass(
    name: "GameScore"
    schemaFields: {
      addStrings: [{ name: "playerName" }]
      addNumbers: [{ name: "score" }]
      addBooleans: [{ name: "cheatMode" }]
    }
  ) {
    name
    schemaFields {
      name
      __typename
    }
  }
}
```

You should receive the following response:

```json
{
  "data": {
    "createClass": {
      "name": "GameScore",
      "schemaFields": [
        {
          "name": "objectId",
          "__typename": "SchemaStringField"
        },
        {
          "name": "updatedAt",
          "__typename": "SchemaDateField"
        },
        {
          "name": "createdAt",
          "__typename": "SchemaDateField"
        },
        {
          "name": "playerName",
          "__typename": "SchemaStringField"
        },
        {
          "name": "score",
          "__typename": "SchemaNumberField"
        },
        {
          "name": "cheatMode",
          "__typename": "SchemaBooleanField"
        },
        {
          "name": "ACL",
          "__typename": "SchemaACLField"
        }
      ]
    }
  }
}
```

## Using automatically generated operations

Parse Server learned from the first class that you created and now you have the `GameScore` class in your schema. You can now start using the automatically generated operations!

Run the following to create your first object:

```graphql
mutation CreateGameScore {
  createGameScore(
    fields: {
      playerName: "Sean Plott"
      score: 1337
      cheatMode: false
    }
  ) {
    id
    updatedAt
    createdAt
    playerName
    score
    cheatMode
    ACL
  }
}
```

You should receive a response similar to this:

```json
{
  "data": {
    "createGameScore": {
      "id": "XN75D94OBD",
      "updatedAt": "2019-09-17T06:50:26.357Z",
      "createdAt": "2019-09-17T06:50:26.357Z",
      "playerName": "Sean Plott",
      "score": 1337,
      "cheatMode": false,
      "ACL": null
    }
  }
}
```

You can also run a query to this new class:

```graphql
query GameScores {
  gameScores {
    results {
      id
      updatedAt
      createdAt
      playerName
      score
      cheatMode
      ACL
    }
  }
}
```

You should receive a response similar to this:

```json
{
  "data": {
    "gameScores": {
      "results": [
        {
          "id": "XN75D94OBD",
          "updatedAt": "2019-09-17T06:50:26.357Z",
          "createdAt": "2019-09-17T06:50:26.357Z",
          "playerName": "Sean Plott",
          "score": 1337,
          "cheatMode": false,
          "ACL": null
        }
      ]
    }
  }
}
```

## Customizing your GraphQL Schema

Parse GraphQL Server allows you to create a custom GraphQL schema with own queries and mutations to be merged with the auto-generated ones. You can resolve these operations using your regular cloud code functions.

To start creating your custom schema, you need to code a `schema.graphql` file and initialize Parse Server with `--graphQLSchema` and `--cloud` options:

```bash
$ parse-server --appId APPLICATION_ID --masterKey MASTER_KEY --databaseURI mongodb://localhost/test --publicServerURL http://localhost:1337/parse --cloud ./cloud/main.js --graphQLSchema ./cloud/schema.graphql --mountGraphQL --mountPlayground
```

### Creating your first custom query <!-- omit in toc -->

Use the code below for your `schema.graphql` and `main.js` files. Then restart your Parse Server.

```graphql
# schema.graphql
extend type Query {
  hello: String! @resolve
}
```

```js
// main.js
Parse.Cloud.define('hello', async () => {
  return 'Hello world!';
});
```

You can now run your custom query using GraphQL Playground:

```graphql
query {
  hello
}
```

You should receive the response below:

```json
{
  "data": {
    "hello": "Hello world!"
  }
}
```

## Learning more

The [Parse GraphQL Guide](http://docs.parseplatform.org/graphql/guide/) is a very good source for learning how to use the Parse GraphQL API.

You also have a very powerful tool inside your GraphQL Playground. Please look at the right side of your GraphQL Playground. You will see the `DOCS` and `SCHEMA` menus. They are automatically generated by analyzing your application schema. Please refer to them and learn more about everything that you can do with your Parse GraphQL API.

Additionally, the [GraphQL Learn Section](https://graphql.org/learn/) is a very good source to learn more about the power of the GraphQL language.

# Upgrading to 3.0.0

Starting 3.0.0, parse-server uses the JS SDK version 2.0.
In short, parse SDK v2.0 removes the backbone style callbacks as well as the Parse.Promise object in favor of native promises.
All the Cloud Code interfaces also have been updated to reflect those changes, and all backbone style response objects are removed and replaced by Promise style resolution.

We have written up a [migration guide](3.0.0.md), hoping this will help you transition to the next major release.

# Want to ride the bleeding edge?

It is recommend to use builds deployed npm for many reasons, but if you want to use
the latest not-yet-released version of parse-server, you can do so by depending
directly on this branch:

```
npm install parse-community/parse-server.git#master
```

## Experimenting <!-- omit in toc -->

You can also use your own forks, and work in progress branches by specifying them:

```
npm install github:myUsername/parse-server#my-awesome-feature
```

And don't forget, if you plan to deploy it remotely, you should run `npm install` with the `--save` option.

# Contributing

We really want Parse to be yours, to see it grow and thrive in the open source community. Please see the [Contributing to Parse Server guide](CONTRIBUTING.md).

# Contributors

This project exists thanks to all the people who contribute... we'd love to see your face on this list!

<a href="../../graphs/contributors"><img src="https://opencollective.com/parse-server/contributors.svg?width=890&button=false" /></a>

# Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [Become a sponsor!](https://opencollective.com/parse-server#sponsor)

<a href="https://opencollective.com/parse-server/sponsor/0/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/1/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/2/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/3/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/4/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/5/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/6/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/7/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/8/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/9/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/9/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/10/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/10/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/11/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/11/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/12/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/12/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/13/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/13/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/14/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/14/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/15/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/15/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/16/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/16/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/17/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/17/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/18/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/18/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/19/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/19/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/20/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/20/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/21/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/21/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/22/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/22/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/23/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/23/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/24/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/24/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/25/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/25/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/26/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/26/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/27/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/27/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/28/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/28/avatar.svg"></a>
<a href="https://opencollective.com/parse-server/sponsor/29/website" target="_blank"><img src="https://opencollective.com/parse-server/sponsor/29/avatar.svg"></a>

# Backers

Support us with a monthly donation and help us continue our activities. [Become a backer!](https://opencollective.com/parse-server#backer)

<a href="https://opencollective.com/parse-server#backers" target="_blank"><img src="https://opencollective.com/parse-server/backers.svg?width=890" /></a>

-----

As of April 5, 2017, Parse, LLC has transferred this code to the parse-community organization, and will no longer be contributing to or distributing this code.
