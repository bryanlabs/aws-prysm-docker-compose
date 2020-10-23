# aws-prysm-docker-compose
This repository makes it easy to install [stefa2k/prysm-docker-compose](https://github.com/stefa2k/prysm-docker-compose) on AWS (Amazon Web Services).

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=PrysmValidator&templateURL=https://bryanlabs-public.s3.amazonaws.com/validator.yml)

Or learn how to deploy cloudformation templates from the console    
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html  

Connect to instance using Session Manager (skip to step3, this tool takes care of step 1 and 2)  
https://medium.com/@korniichuk/session-manager-e724eb105eb7

Once your in
```
sudo su - ubuntu

```
## Import your wallet

Sync your wallet  

```
#Sync Wallet
rsync -avzh walletlocation/validator/* ~/.eth2validators/prysm-wallet-v2/validator/
```
