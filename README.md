# aws-prysm-suite  
## Install Prysm Validator on AWS (Amazon Web Services).
Launching this template will build a VPC (Virtual Private Cloud) to run the Prysm client. The client runs on EC2, and includes geth, beacon-chain, and validator.  The stack accepts several inputs to allow you to customize the CLI options for each service. After launching, you can view the Prysm Web UI, and Grafana Display by looking at the Cloudformation Outputs. (Details below).

## Security
The EC2 instance is protected by both a Keypair, and a Network Access List.  Please use the following link to create a key, and [Import the Public Keypair ](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#prepare-key-pair) to AWS.  During the stack launch you can change `TrustedCIDR` to match the IP address of a trusted location.


## Installation
The entire stack can be installed by logging into your AWS Account, and then clicking this link.  By default, the only option you have to explicitly set is your Keypair, but everything else can be highly customized to meet the demands of the network.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=PrysmValidator&templateURL=https://bryanlabs-public.s3.amazonaws.com/validator.yml)

## Accessing Your Node
As mentioned above, everything is protected by SSH using a Keypair, and Trusted Address range.  In order to interact with the Grafana Dashboard, and Prysm Web UI port forwarding is needed. If you have any trouble connecting, read [Connect to instance using SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

```
ssh -Xi keys/private.pem -L 3500:127.0.0.1:3500 -L 7500:127.0.0.1:7500 ubuntu@x.x.x.x
```


## Import your wallet
By default this tool expects your wallet to be `~/.eth2validators/prysm-wallet-v2`.  The Prysm WebUI can be used to create, or import your wallet.  Alternatively you can create your wallet by Connecting to the instance, and following
https://docs.prylabs.network/docs/prysm-usage/running-a-validator#creating-your-wallet

