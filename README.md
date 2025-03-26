**Ticket Type:** Task  
**Title:** Terraform Variables  
**Project:** Version Control System Deployment  
**Assignee:** You  
**Reporter:** Derek Morgan  
**Priority:** High  
**Labels:** Terraform, GitHub, Variables, Validation  
**Epic Link:** GitHub Expansion  
**Sprint:** Sprint 01/Variables

**Description:**

The variables for the deployment of our repository need a validation mechanism to ensure they are defined correctly by the engineers. Using the acceptance criteria below, add a validation block to each variable to restrict the values that can be used for the variable. If you don’t have a repository already, deploy one using the variables in the acceptance criteria. 

**Acceptance Criteria:**

> **Note:** If the `terraform validate` command fails, all tasks in the lab will fail!

1\. In `main.tf`, create a repository with Terraform. For the name, use “project” and “env” variables to construct a name separated by a hyphen. E.g. `infrastructure-dev`  
2\. Create a `project` variable for the name of the project. This should only accept values of `frontend infrastructure` or `backend`.   
3\. Create an `env` variable with possible values of `dev` or `prod`.   
4\. Create an `auto_init` variable with possible values of `true` or `false`. Do this as simply as possible.   
5\. Create a `gitignore` variable and ensure its only possible values are `Terraform`, `Python`, or `Node`. 

**Implementation Notes:**

This should all be accomplished using variable validation blocks. You may need to use a function to set the possible values. 

- <a href="https://registry.terraform.io/providers/integrations/github/latest/docs" target="_blank">GitHub Provider Documentation</a>  
- <a href="https://developer.hashicorp.com/terraform/language/functions/contains" target="_blank">contains() Function</a>  
- <a href="https://developer.hashicorp.com/terraform/language/expressions/types" target="_blank">Terraform Type System</a>  
- <a href="https://developer.hashicorp.com/terraform/language/values/variables#custom-validation-rules" target="_blank">Variable Validation Rules</a>
