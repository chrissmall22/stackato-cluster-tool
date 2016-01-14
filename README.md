# stackato-cluster-tool
Terraform a Stackato cluster on Amazon AWS (later Virtualbox).

##### 1. Install Terraform
https://terraform.io/downloads.html

##### 2. Setup your Stackato cluster
- Choose the Stackato version to deploy by copying stackato-version/var-stackato-xxx.tf into the root folder (folder containing config.tf)
- Choose your cluster configuration in config.tf. The name of the cluster (key cluster_name) will be asked while launching Terraform

###### For an Amazon cluster
- Copy the content of the `amazon-aws` directory into the root directory of the project
- Choose your Amazon configuration in config-amazon.tf, especially aws_access_key and aws_secret_key. Check the Amazon documentation http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSGettingStartedGuide/AWSCredentials.html to get those two keys.
- Make sure you uploaded your public SSH key (see doc: http://docs.aws.amazon.com/gettingstarted/latest/wah/getting-started-prereq.html#create-a-key-pair) and update the variable `ssh_key_name` in config-amazon.tf

##### 3. Start the cluster
In a terminal, move to the root directory containing the Terraform files.

Check that the configuration from step 2 is valid by running `terraform plan`.

Start the cluster by running `terraform apply`.

##### 4. Modify a running cluster
You can update the configuration file config.tf then run `terraform plan` and `terraform apply` again.

##### 5. Destroy a cluster
Run the command `terraform destroy` and type 'yes'.
