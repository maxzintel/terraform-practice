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

#### My Current Tech Stack - What I use and what I am learning.
*Inspired by Cloud Native.*
* **App Definition and Development**
  * Databases:
    * Cockroach,
    * Redis,
    * Mongo
  * Streaming and Messages:
    * RabbitMQ
  * App Definition and Image Build:
    * docker-compose,
    * Helm
  * CI/CD:
    * GitLab,
    * Jenkins,
    * Bamboo,
    * Azure Pipelines,
    * TravisCI,
    * Heroku
* **Orchestration and Management**
  * Scheduling and Orchestration:
    * Kubernetes
  * Coordination and Service Discovery:
    * etcd
  * Service Proxy
    * nginx
* **Runtime**
  * Cloud Native Network:
    * Calico,
    * Flannel
* **Provisioning**
  * Automation and Config:
    * Terraform
  * Container Registry:
    * Harbor,
    * Docker,
    * Azure,
    * Kraken
  * Security and Compliance:
    * cert-manager,
    * Notary,
    * OPA,
    * TUF
  * Key Management:
    * Vault
* **Platform**
  * Distribution:
    * Docker,
    * Typhoon
* **Observation and Analysis**
  * Monitoring:
    * prometheus
  * Logging:
    * Splunk,
    * fluentd,
    * logstash
  * Chaos Engineering:
    * chaostoolkit,
    * Gremlin
