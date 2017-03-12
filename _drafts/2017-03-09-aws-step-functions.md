---
layout:     post
title:      AWS Step Functions fail at scale
date:       2017-03-09 12:32:18
summary:    hidden limitations of step functions at scale
categories: aws data
---

AWS Lambda functions, each performing a well-defined task are a great way to implement a micro-service that can scale. Lambda Functions free you from thinking about how many requests per second your infrastructure needs to support. No need to worry about installing the right runtime or supported libariries. Simply package you function with its dependencies and specify the runtime: Java or Python.

So, when Amazon realses a service purported to orchestrate Lambda functions at scale, I get excited. Stringing together Lambda functions, each with a core, well-tested task coordinated to perform a much more complex task---amazing!

I'm pissed. After investing in a serverless architecture powered by Amazon's marvelous sounding Lambda functions orchestrated by their newly advertised service, Step Functions, I ran into a roadblock.
Articles such as this [aws blog post](https://aws.amazon.com/blogs/aws/new-aws-step-functions-build-distributed-applications-using-visual-workflows/) 
tout AWS Step Functions as a service that "will let you run thousands of execution concurrently so you can scale to any desired level." 

Surely, a simple process checking if a field is present in a DynamoDB record is supported?

Failings
bullet 
bullet
bullet






