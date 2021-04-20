+++
title = "AWS - Infrastructure as Code with CloudFormation"
slug = "aws-cloudformation"
layout = "page.html"
date = 2021-04-15
draft = true
[taxonomies]
tags = ["aws", "cloudformation"]
+++

Manual steps:
1. Create a access KeyPair in your AWS account. A KeyPair must be set manually othewise won't be able to access the machines you create with your CF template in the CF stack.
2. Upload CF template
	- Specify Stack details
	AWS Management Console -> CloudFormation -> Create Stack -> give it a stack name -> Fill in parameters -> Select Keypair you've created from step 1
	- Configure Stack Options
	More config
	- Review
	Create Stack
