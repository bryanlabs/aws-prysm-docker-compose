# aws-prysm-suite  
## Install Prysm Validator on AWS (Amazon Web Services).

[Import or Create A Keypair ](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#prepare-key-pair)

then 

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=PrysmValidator&templateURL=https://bryanlabs-public.s3.amazonaws.com/validator.yml)

## Access the Shell

[Connect to instance using SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

```
ssh -Xi privatekey.pem ubuntu@publicip
```

[Connect to instance using Session Manager](https://medium.com/@korniichuk/session-manager-e724eb105eb7)

Once your in, switch to ubuntu user
```
sudo su - ubuntu
```
## Import your wallet

Sync your wallet  

```
#Sync Wallet
rsync -avzh walletlocation/validator/* ~/.eth2validators/prysm-wallet-v2/validator/
```
