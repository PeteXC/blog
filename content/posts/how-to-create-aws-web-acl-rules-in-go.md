---
title: "How to create an AWS WAF in Go CDK"
author: "Peter C"
date: "2022-04-29T20:03:56+01:00"
draft: false
cover: "/img/rules.jpg"
coverCaption: "Photo by Kyle Glenn on Unsplash"
description: "A short guide on how to create an AWS WAF and write custom web ACL rules in Go CDK"
Categories: ["archive"]
---

Recently I've been creating some custom AWS WAF rules to workaround the not so well known [AWS WAF limit](https://docs.aws.amazon.com/waf/latest/developerguide/web-request-body-inspection.html) of 8 kilobytes on the inspection of web request bodies.

To start with, a WAF is a Web Application Firewall. It's a layer that scans and monitors the HTTP requests between your content distribution network (CDN) and the rest of the internet. Typically it sits on top of Cloudfront if we're talking about AWS.

You can configure a WAF with rules that will dictate the behaviour of the firewall. Block some requests if theses conditions are met... Allow these other requsts if these other conditions are met... etc

If you're reading this post, you will likely already have a good understanding of all of this anyways so I'll just cut to the chase. How can one use AWS CDK to create a WAF?

## Create a CDK project

Let's start by creating an empty cdk.go file and run the following to initialise a go module for this project with `go mod init`

We can start by importing the Go CDK package for AWS WAF at [awswafv2](https://pkg.go.dev/github.com/aws/aws-cdk-go/awscdk/v2/awswafv2) right into our cdk.go file:

```
import 	"github.com/aws/aws-cdk-go/awscdk/v2/awswafv2"
```

Or you could use the older version:

```
import "github.com/aws/aws-cdk-go/awscdk/awswafv2"
```

and some code to get you started:

```go
func main() {
	app := awscdk.NewApp(nil)

    stack := awscdk.NewStack(app, "WAFStack", &CDNStackProps{
        StackProps: awscdk.StackProps{
			Env: &awscdk.Environment{
				Account: jsii.String("{Your account here}"),
				Region:  jsii.String("us-east-1")
			},
		},
    })
	app.Synth(nil)
}
```

Note that Cloudfront WAFs [must be in us-east-1](https://docs.aws.amazon.com/waf/latest/developerguide/how-aws-waf-works.html) as of the writing of this article.

## Create a WAF

```go
func createWAF(stack awscdk.Stack, rules interface{}) {
	awswafv2.NewCfnWebACL(stack, jsii.String("MyWebACLId"), &awswafv2.CfnWebACLProps{
		Name:  jsii.String("MyWebACLName"),
		Scope: jsii.String("CLOUDFRONT"),
		DefaultAction: awswafv2.CfnWebACL_DefaultActionProperty{
			Allow: struct{}{},
		},
		VisibilityConfig: awswafv2.CfnWebACL_VisibilityConfigProperty{
			SampledRequestsEnabled:   true,
			CloudWatchMetricsEnabled: true,
			MetricName:               jsii.String("MyWebACLName"),
		},
		Rules: rules,
	})
}
```

Now call this method in your main method before `app.Synth(nil)` and you're golden!

But hold-up, you still haven't got any rules to add to your web ACL!

## Create rules for the Web ACL

To understand how Web ACL rule priority works read [this](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-processing-order.html) and for how rules work in general the [AWS docs](https://docs.aws.amazon.com/waf/latest/developerguide/waf-rules.html) I would recommend reading. It's fairly straighforward and the basic structure of a rule looks like this

1. 

