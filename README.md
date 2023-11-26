# Stateful vs. stateless workloads with IaC: Together or not?

## Context

This repository is the main asset for the *AWS re:Invent 2023* chalk talk titled: "*Stateful vs. stateless workloads with IaC: Together or not?*" (**[BOA206](https://hub.reinvent.awsevents.com/attendee-portal/catalog/?search=boa206)**).

## Resources

- [Session resource: Mind Map (JPG)](./docs/stateful-vs-stateless-workloads-with-iac-mind-map.jpg)
- [Session resource: Mind Map (PDF)](./docs/stateful-vs-stateless-workloads-with-iac-mind-map.pdf)

## 1 Pager

## Stateful vs Stateless - 1 pager copy

### 1. Purpose

This document provides an overview of managing stateful and stateless workloads using Infrastructure as Code. The objective of this initiative is to provide a holistic approach, outlining guidance on application processes and future change considerations. It will be refined by the main team and it will take into account community feedback and technological advancements.

### 2. Background and defining the initiative scope

Working with stateful and stateless workloads has experienced a shift when Infrastructure as Code (IaC) was introduced. Current landscape of multiple IaC tools, different working frameworks, and constant changes in the tech world pushes for thorow research and experience in order to make decision whether stateful/stateless workloads should be kept together or not.

#### Stateful vs. Stateless Mechanism 
Working backwards from personal experiences and customers feedback, a centralised approach was clearly needed to bring in one place a way to handle this decision in a well-informed manner:
 
**1/ Terminology definitions:** Setting up a common place to start, clearing all interpretations, and list the concepts. See Appendix 2.

**2/ Business outlines:** Taking into account the customers ways of working, preferred organizational structure, and its people.

**3/ Workload types:** Definitions for both types, followed by a deep dive into the stateful scenario.
 
#### Discovery Questions

(1) Are you using Infrastructure as Code?

(2) Are your teams focused on a product or are the responsibilities split between multiple teams (Developers Team, Operations Team, Infrastructure Team)?

(3) Who has ownership over the infrastructure? (a) Is the Delivering team not in charge of infrastructure? Is there any exception like: Is Delivering Team in charge of the infrastructure of Test/Development Environments? (b) Is the Delivering Team cross-functional and has full ownership over the infrastructure it needs? OR (c) Is the ownership split between the Delivery Team and other technical tea, (Ops/Infra)? How are they working together: is there an environment-level split, clear cut-off abstraction layer, or is there a hand-off between teams?

(4) What is your people level of skills and experiences? Are there any tooling preferences: team-wide or organization-wide? What is the seniority in the role for the existing team members? Do you have any past experiences that might indicate the need of a particular tools? (for example, the team needs a tool for automated rollback in case accidents happen in the IaC or Cloud Automation process) 
 
This question should guide customers in the right direction when making the decision to use Stateful/Stateless workloads together or not. 
 
#### Next steps
Next steps include 1/Contribute: Share your experiences and blocking points along the road. 2/Actively gathering feedback: Starting with this re:Invent talk the initiative will actively be maintained to stay relevant in case of any particular use cases or any new technological advancements that might happen in the future. 

### 3. Appendix

#### Appendix 1: 
See Mind Map 
 
#### Appendix 2: Definitions
**State** is the information a system holds at any given point.

**SIDE EFFECTS** are a primary way of identifying impact of a change that was invoked on a cloud resource. The consequences of a side effect are: you lose the state and that cannot be recreated in the identical forms using IaC or Cloud Automation alone. 

**Stateless** resource is a replaceable cloud resource, on which all of the mutable operations (modification/creation/destruction) do not introduce any side-effects on the other infrastructure and application components that are interconnected (dependent) with it inside the resource graph.

**Stateful** resource is a cloud resource, that on which any mutable operation (modification/creation/destruction) will ripple side-effects on the other infrastructure and application components that are interconnected (dependent) with it inside the resource graph.

**Idempotency** is a characteristic of a given operation to always produce the same result.

**Provisioning** is the process of setting up infrastructure in the cloud.

**Immutable Infrastructure** is a type of infrastructure that can’t be modified once provisioned and can only be replaced.

**Infrastructure as code** is a way to create infrastructure resources from code. There are two main flavours of IaC: (1) Resource-oriented: AWS CloudFormation (State of the resources is Handled Implicitly), Terraform / OpenTofu (State of the resources is handled Explicitly), (2) Code-Oriented: AWS CDK, Pulumi, Klotho, Winglang. For the second one, there are alternative names such as Infrastructure as real Code or Infrastructure from Code.

**Cloud Automation** is a process of orchestrating IaC, provisioning, and configuring in an automated way your cloud resources.


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This repository is licensed under the *MIT-0* License. See the [LICENSE](LICENSE) file.
