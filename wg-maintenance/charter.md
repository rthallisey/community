# WG Maintenance Charter

This charter adheres to the conventions described in the [Kubernetes Charter README] and uses
the Roles and Organization Management outlined in [wg-governance].

[Kubernetes Charter README]: /committee-steering/governance/README.md

## Scope

Enhance support for Maintenance in Kuberenentes. Specifially, this working
group will focus on ideas, methods, APIs, and tooling that will improve
the end-user experience for day-2 management operations in Kubernetes.

The ecosystem for doing maintenance already exists around Kubernetes. This
working group would coalesce what exists and direct it towards improving
APIs and tools.

### In scope

- Enable Node Maintenance.
- Enable Non-Node Maintenance (maintenance on infrastructure that is not
  represented by the Node API).
- Enable the scheduler decide where a workload should land based on planned or ongoing Maintenance.
- Enable autoscalers to choose whether to create additional resources due to planned or ongoing Maintenance.
- Provide a state defintion for Maintenance in Kubernetes.
- Minimize workload disruption due to Maintenance.
- Provide an API to express Maintenance in Kubernetes.

### Out of scope

- Tooling that will do maintenance. That will be left to the end-user to create.
- General day-2 managment solution.

## Stakeholders

- SIG Architecture
- SIG Autoscaling
- SIG Node
- SIG Scheduling

Stakeholders span from multiple SIGs to a broad set of end users,
public and private cloud providers, Kubernetes distribution providers,
and cloud provider end-users. Here are some user stories:

- End users cannot bear the cost of blue-green upgrades, especially with special
  hardware accelerators; it's far too expensive.  It more cost effective to coordinate
  a drain, then upgrade.
- Cloud providers do regular maintenance on the hardware in the fleet. Enhancing
  Kubernetes to help providers safely remove hardware will help with operational
  cost.
- Modeling the cost of doing accelerator maintenance in todays world can be massive.
  And since hardware accelerators tend to need more love and care, having software
  support to coordinate maintenance will reduce operational cost.

## Deliverables

The WG will coordinate requirement gatherthing and design, eventually leading to
KEP(s)s and code associated with the ideas.

Area we expect to explore:

- An API that describes Maintenance.
- An API that expresses the intention to drain workloads.
- Writing code across multiple sigs to add Maintenance support in native K8s
  APIs and services.
- Teaching the Scheduler and AutoScalers how to plan based on recent and future
  maintenance activity.

## Roles and Organization Management

This WG adheres to the Roles and Organization Management outlined in [wg-governance]
and opts-in to updates and modifications to [wg-governance].

[wg-governance]: /committee-steering/governance/wg-governance.md

## Timelines and Disbanding

The working group will disband when the KEPs we create are completed. We will
review whether the working group should disband if appropriate SIG ownership
can't be reached.
