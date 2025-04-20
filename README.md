**Ticket Type:** Task  
**Title:** Terraform Variable Validation with AWS VPC  
**Project:** Cloud Infrastructure Deployment  
**Assignee:** You  
**Reporter:** Derek Morgan  
**Priority:** High  
**Labels:** Terraform, AWS, Variables, Validation, VPC  
**Epic Link:** AWS Infrastructure Expansion  
**Sprint:** Sprint 01/Variables

**Lab Setup**
This lab uses Localstack to simulate an AWS environment. Localstack is already preinstalled in your environment. You don't need keys or to configure the provider. If you'd like to use your own account, feel free to specify your provider configuration and run `unset aws` and `unset terraform` to decouple them from Localstack.

**Description:**

Your team needs to set up a new Virtual Private Cloud (VPC) in AWS with strict configuration requirements. The variables for the VPC deployment need a validation mechanism to ensure they are defined correctly by the engineers. Using the acceptance criteria below, add a validation block to each variable to restrict the values that can be used for the variable.

**Acceptance Criteria:**

> **Note:** If the `terraform validate` command fails, all tasks in the lab will fail!

1. In `main.tf`, create an AWS VPC resource with Terraform. For the name tag, use "project" and "env" variables to construct a name separated by a hyphen. E.g. `infrastructure-dev`  
2. Create a `project` variable for the name of the project. This should only accept values of `frontend`, `infrastructure`, or `backend`.   
3. Create an `env` variable with possible values of `dev` or `prod`.   
4. Create an `enable_dns_hostnames` variable with possible values of `true` or `false`. Do this as simply as possible (hint: consider what type would naturally restrict values to true/false).   
5. Create a `cidr_block` variable and ensure its only possible values are `10.0.0.0/16`, `10.0.0.0/18`, or `10.0.0.0/20`.

**Implementation Notes:**

This should all be accomplished using variable validation blocks. You may need to use a function to set the possible values. 

- <a href="https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc" target="_blank">AWS VPC Resource Documentation</a>  
- <a href="https://developer.hashicorp.com/terraform/language/functions/contains" target="_blank">contains() Function</a>  
- <a href="https://developer.hashicorp.com/terraform/language/expressions/types" target="_blank">Terraform Type System</a>  
- <a href="https://developer.hashicorp.com/terraform/language/values/variables#custom-validation-rules" target="_blank">Variable Validation Rules</a>
