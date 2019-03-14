---
layout: post
title: "Building a serverless pet project: Part I"
date: 2019-02-26 20:32:44
image: '/assets/img/'
description: 'Running a dedicated web app at next to no cost'
tags:
- aws
- lambda
- backend
categories:
- Backend development
twitter_text: 'Serverless pet projects and AWS Lambda Part I'
---
# Why ?
I've had a couple opportunities to become involved with "pet projects" either through personal interests or hackathons.
They've been awesome ways to get my hands dirty with newer technologies like Angular and Firebase that aren't typically
learned in CS degree programs, but managing the deployment of these apps is a hassle. As a student, I didn't want to have
to worry about the configuration management that comes with running a dedicated cloud server like an AWS EC2 instance, and
a dedicated instance is using a lot of compute time that my small project would really not need due to the lack of consistent
traffic. `That being said, it's nice to deploy pet projects in order to showcase a polished version of a web app to friends
or prospective employers without worrying if your instance is running or if you've stopped it.

Enter serverless web apps! Instead of managing a running instance, and paying for unused compute time, you write "functions"
in the backend language of your choice (*ehhhh* with a catch), and your cloud provider will manage an environment for
that function to run on, taking care of all the configuration details. The caveat is that some overhead goes into spinning
up an environment to run your function when it is called by some type of trigger (an API for example), particularly if it
hasn't been run in some time. This results in some additional latency when compared with a dedicated cloud server, but for
the use case described here this isn't really noticeable enough to be an issue (at least it wasn't for me).

Disclaimer: serverless computing is becoming very popular, but it's absolutely not a catch-all solution (especially not yet) and should be evaluated according your specific use case.

In this guide, I'll be walking through some of the steps needed to deploy a serverless API to AWS as this is my cloud provider of choice, but there are valid reasons to choose any of the major cloud providers. Here are links to the largest ones:

* [AWS Lambda](https://aws.amazon.com/lambda) seems to lead the pack because AWS is still the most popular cloud provider right
now. They support a ton of languages and have a lot of libraries pre-installed in their runtime environment.
* [Google Cloud Functions](https://cloud.google.com/functions/) are Google Cloud's serverless function tool. For projects that want to natively
integrate with other GCP services this seems like a good choice, but as of this writing functions have to be written in NodeJS which is a legitimate hangup.
* [IBM Cloud Functions](https://www.ibm.com/cloud/functions) supports serverless functions as well. I have no experience with IBM cloud,
but they appear to be competitive with AWS Lambda for those who already have tools on the IBM Cloud platform.
* [Microsoft Azure Functions](https://azure.microsoft.com/en-us/services/functions/) for use with Microsoft Azure. Like with IBM and GCP functions,
choosing Azure functions is the obvious choice if you're more experienced with the Microsoft Cloud.

*to be continued...*

## Sample Lambda function

{% highlight python %}

def lambda_handler(event, context):
    # API Gateway will trigger and pass the details of the request in the 'event' argument
    user_id = event["queryStringParameters"]['user']

    # ensure that there was valid input
    if (user_id is None):
        return {
            'statusCode': 400,
            'body': 'Error: User ID was not provided.'
        }

    user = get_user(user_id)

    if (user is None):
        return {
            'statusCode': 404,
            'body': 'Error: User was not found.'
        }

    return {
        'statusCode': 200,
        'body': json.dumps(user)
    }

{% endhighlight %}