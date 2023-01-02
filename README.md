[![Serverless Application Framework AWS Lambda API Gateway](https://s3.amazonaws.com/assets.github.serverless/readme-serverless-framework.gif)](https://serverless.com)

[![serverless](http://public.serverless.com/badges/v3.svg)](http://www.serverless.com)
[![Build Status](https://github.com/serverless/serverless/workflows/Integrate/badge.svg)](https://github.com/serverless/serverless/actions?query=workflow%3AIntegrate)
[![npm version](https://badge.fury.io/js/serverless.svg)](https://badge.fury.io/js/serverless)
[![codecov](https://codecov.io/gh/serverless/serverless/branch/master/graph/badge.svg)](https://codecov.io/gh/serverless/serverless)
[![gitter](https://img.shields.io/gitter/room/serverless/serverless.svg)](https://gitter.im/serverless/serverless)
[![Known Vulnerabilities](https://snyk.io/test/github/serverless/serverless/badge.svg)](https://snyk.io/test/github/serverless/serverless)
[![license](https://img.shields.io/npm/l/serverless.svg)](https://www.npmjs.com/package/serverless)
[![Unzip.dev](https://img.shields.io/badge/Featured%20on-Unzip.dev-fa2367)](https://unzip.dev/0x004-infrastructure-as-code/#tools-players-%F0%9F%9B%A0%EF%B8%8F)

[Website](http://www.serverless.com) • [Docs](https://serverless.com/framework/docs/) • [Community Slack](https://serverless.com/slack) • [Forum](http://forum.serverless.com) • [Twitter](https://twitter.com/goserverless) • [Meetups](https://www.meetup.com/pro/serverless/) • [We're Hiring](https://serverless.com/company/jobs/) • [简体中文](./README_CN.md)

**The Serverless Framework** – Build applications on AWS Lambda and other next-gen cloud services, that auto-scale and only charge you when they run. This lowers the total cost of running and operating your apps, enabling you to build more and manage less.

The Serverless Framework is a command-line tool that uses easy and approachable YAML syntax to deploy both your code and cloud infrastructure needed to make tons of serverless application use-cases. It's a multi-language framework that supports Node.js, Typescript, Python, Go, Java, and more. It's also completely extensible via over 1,000 plugins that can add more serverless use-cases and workflows to the Framework.

Actively maintained by [Serverless Inc](https://www.serverless.com).

## Contents

- [Quick Start](#quick-start)
- [Features](#features)
- [Plugins](https://github.com/serverless/plugins)
- [Contributing](#contributing)
- [Community](#community)
- [Licensing](#licensing)
- [Previous Version 0.5.x](#v.5)

## <a name="quick-start"></a>Quick Start

### Installation

Install the `serverless` CLI via NPM:

```bash
npm install -g serverless
```

Note: If you don’t already have Node on your machine, [install it first](https://nodejs.org/). If you don't want to install Node or NPM, you can [install `serverless` as a standalone binary](https://www.serverless.com/framework/docs/install-standalone).

### Getting started

To create your first project, run the command below and follow the prompts:

```bash
# Create a new serverless project
serverless

# Move into the newly created directory
cd your-service-name
```

The `serverless` command will guide you to:

1. create a new project
2. configure [AWS credentials](https://serverless.com/framework/docs/providers/aws/guide/credentials/)
3. optionally set up a free [Serverless Dashboard](https://www.serverless.com/monitoring) account to monitor and troubleshoot your project

_Note: users based in China get a setup centered around the chinese [Tencent](https://intl.cloud.tencent.com/) provider. To use AWS instead, set the following environment variable: `SERVERLESS_PLATFORM_VENDOR=aws`._

Your new serverless project should contain a `serverless.yml` file. This file defines what will be deployed to AWS: functions, events, resources and more. You can learn more about this in the [Core Concepts documentation](https://www.serverless.com/framework/docs/providers/aws/guide/intro).

If the templates proposed by `serverless` do not fit your needs, check out the [project examples from Serverless Inc. and our community](https://www.serverless.com/examples/). You can install any example by passing a GitHub URL using the `--template-url` option:

```sh
serverless --template-url=https://github.com/serverless/examples/tree/v3/...
```

### Deploying

If you haven't done so already within the `serverless` command, you can deploy the project at any time by running:

```bash
serverless deploy
```

The deployed functions, resources and URLs will be displayed in the command output.

[Learn more about deploying](https://www.serverless.com/framework/docs/providers/aws/guide/deploying).

### Invoking function

If you deployed an API, querying its URL will trigger the associated Lambda function. You can find that URL in the `serverless deploy` output, or retrieve it later via `serverless info`.

If you deployed a function that isn't exposed via a URL, you can invoke it via:

```bash
serverless invoke -f hello

# Invoke and display logs:
serverless invoke -f hello --log
```

### Fetching function logs

All logs generated by a function's invocation are automatically stored in AWS CloudWatch. Retrieve those logs in the CLI via:

```bash
serverless logs -f hello

# Tail logs
serverless logs -f hello --tail
```

### Monitoring

You can monitor and debug Lambda functions and APIs via the [Serverless Dashboard](https://www.serverless.com/monitoring).

To set it up, run the following command in an existing project and follow the prompts:

```bash
serverless
```

### Remove your service

If you want to delete your service, run `serverless remove`. This will delete all the AWS resources created by your project and ensure that you don't incur any unexpected charges. It will also remove the service from Serverless Dashboard.

```bash
serverless remove
```

## What's next

Now that Serverless Framework is installed, here is what you can do next:

- Follow the [tutorial to create an example HTTP API with Node](https://www.serverless.com/framework/docs/tutorial)
- Learn about the [core concepts in Serverless Framework](https://www.serverless.com/framework/docs/providers/aws/guide/intro)
- [Redeploy a single function](https://www.serverless.com/framework/docs/providers/aws/guide/deploying#deploy-function) for iterating faster while developing
- Discover all the [events that can trigger Lambda functions](https://www.serverless.com/framework/docs/providers/aws/guide/events)
- Check out the [plugins registry](https://www.serverless.com/plugins)

## <a name="features"></a>Features

- Supports Node.js, Python, Java, Go, C#, Ruby, Swift, Kotlin, PHP, Scala, & F#
- Manages the lifecycle of your serverless architecture (build, deploy, update, delete).
- Safely deploy functions, events and their required resources together via provider resource managers (e.g., AWS CloudFormation).
- Functions can be grouped ("serverless services") for easy management of code, resources & processes, across large projects & teams.
- Minimal configuration and scaffolding.
- Built-in support for multiple stages.
- Optimized for CI/CD workflows.
- Loaded with automation, optimization and best practices.
- 100% Extensible: Extend or modify the Framework and its operations via Plugins.
- An ecosystem of serverless services and plugins.
- A passionate and welcoming community!

<br>

<table>
  <tr>
    <td align="center">
      <br><strong>Try <a href="https://www.serverless.com/console/">Serverless Console</a></strong><br><br>
      Monitor, observe, and trace your serverless architectures.<br>
      Real-time dev mode provides streaming logs from your AWS Lambda Functions.<br><br>
      Get started instantly with <code>serverless --console</code><br>
      -or-<br>
      <a href="https://bit.ly/3kL8ACL">Register</a>
      <img src="https://user-images.githubusercontent.com/3837103/167449348-bf254fca-9aec-4367-b166-aaa69178f98c.png">
    </td>
  </tr>
</table>

<br>

## <a name="contributing"></a>Contributing

We love our contributors! Please read our [Contributing Document](CONTRIBUTING.md) to learn how you can start working on the Framework yourself.

Check out our [help wanted](https://github.com/serverless/serverless/labels/help%20wanted) or [good first issue](https://github.com/serverless/serverless/labels/good%20first%20issue) labels to find issues we want to move forward on with your help.

## <a name="community"></a>Community

- [Twitter](https://twitter.com/goserverless)
- [Community Slack](https://serverless.com/slack)
- [Serverless Meetups](http://www.meetup.com/serverless/)
- [Stackoverflow](http://stackoverflow.com/questions/tagged/serverless-framework)
- [Facebook](https://www.facebook.com/serverless)
- [Contact Us](mailto:hello@serverless.com)

## <a name="licensing"></a>Licensing

Serverless is licensed under the [MIT License](./LICENSE.txt).

All files located in the node_modules and external directories are externally maintained libraries used by this software which have their own licenses; we recommend you read them, as their terms may differ from the terms in the MIT License.

# <a name="v.5"></a>Previous Serverless Version 0.5.x

You can read the v0.5.x documentation at [readme.io](https://serverless.readme.io/v0.5.0/docs).
