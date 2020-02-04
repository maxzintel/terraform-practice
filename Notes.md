# DevOps Manifesto
* Via the 'Phoenix Project' and 'The Goal', the Theory of Constraints states that every production system is limited by the cadence of the one most significant bottleneck.
  * If the goal of DevOps is to facilitate income via efficient flow of code from development to production, bottlenecks limiting the flow must be improved upon. Each bottleneck must be improved upon until there is another bottleneck with greater affect on the flow.
  * Treat dev and ops like we do car production:
    * At BMW, every vehicle flows along the assembly line at the same cadence as line workers are able to assemble the vehicles and validate quality. We want our code to flow out the door to customers in the same way.
    * Alternatively, if the manufacturing line was consistently slowed by a particular piece of QA or assembly, it would be in the plant's best interests to re-engineer that piece of the manufacturing work flow.
      * I.E. we do not want code to be built every 1-2 days but have to wait 6 days for validation that we can deploy that code. Code should flow through each step of development and deployment at the same cadence. This is largely the reason companies like Amazon have been so successful; Amazon deploys to production many times per day.
* The 12 Factors:
  * A methodology for building software as a service applications.
  * Concisely, SaaS apps should: (via 12factor.net)
    * Use declarative formats for setup automation, to minimize time and cost for new developers joining the project;
    * Have a clean contract with the underlying operating system, offering maximum portability between execution environments;
    * Are suitable for deployment on modern cloud platforms, obviating the need for servers and systems administration;
    * Minimize divergence between development and production, enabling continuous deployment for maximum agility;
    * And can scale up without significant changes to tooling, architecture, or development practices.

**Enter Terraform**

* Terraform, is a _form_ of infrastructure-as-code. Infrastructure as code benefits us in many ways, namely, we:
  * No longer need click around webUI or ssh to a server to manually execute a command.
    * Code is written to define, provision, and manage our infrastructure.
  * Automate our entire provisioning and deployment process. => Faster and more reliable than any manual method.
  * Represent the state of our infrastructure in files that anyone can read! => No more single points of failure, i.e. sysadmin.
  * Store those source files in standard version control. => Our entire infrastructure history is captured via the commit log, which assists with debugging and rollback.
  * Validate each infrastructure change through code reviews and automated tests.
  * May create/buy a library of reusable, documented, battle-tested infrastructure code. => Easier to scale and evolve our infrastructure.

* Why Terraform?
  * Config Management vs Provisioning:
    * Terraform is deisigned to provision servers themselves (plus load balancers, databases, network config)


### Typhooon - TERRAFORM CONCEPTS
* Typhoon config background:
  * Nodes:
    * ALL nodes in cluster provision themselves from the declarative config.
    * Nodes run a `kubelet` servcice and register themselves with the control plane to join the cluster.
    * Run `kube-proxy` and `calico`.
  * Controllers:
    * Controller nodes are scheduled to run the K8s `apiserver`, `scheduler`, `controller-manager`, `coredns`, and `kube-proxy`
    * A fully qualified domain (cluster.maxzintel.dev) resolving to a network load balancer or round-robin DNS is used to refer to the control plane.
  * Workers:
    * workers register with the control plane and run application workloads.
