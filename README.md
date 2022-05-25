# Space Quest League Challenges with Trino 

Welcome to the [Trino](https://trino.io/) getting started tutorial repository - *Space Quest League* edition! 

We challenge you to the [Space Quest League Technical Challenge Event](https://www.starburst.io/info/space-quest-league-sql-challenge/), where for five
weeks we will dive into some SQL challenges that can be completed using this repository!
Completing these challenges will result in fun prizes, as well as bragging rights if you manage to successfully complete the entire series!

Based on @bitsondatadev's legendary [Trino Getting Started Repo](https://github.com/bitsondatadev/trino-getting-started), this is a home for a set of preconfigured [Docker Compose](https://docs.docker.com/compose/) 
environments that are used to set up simple environments and showcase basic 
configurations in isolation to get new and existing users started on all the 
different containers we have, and more importantly learn and have fun with 
Trino.  I dive into all the challenge specific setup in the README located win the trino-minio folder, so if you have docker installed, pop in there and we can get started. 

If you're entirely new to Trino, you're not alone. Trino is a distributed SQL 
query engine designed to query large data sets distributed over one or more 
heterogeneous data sources. Check out some of our [use cases](https://trino.io/docs/current/overview/use-cases.html) 
to understand what Trino is and is not.  We also have a rascally little bunny 
mascot named 
[Commander Bun Bun](https://twitter.com/trinodb/status/1357416368543588356) 🐇.

If you want to learn more about Trino, I highly suggest giving a visit to the Trino Getting Started Repo, where you can explore more capabilities outside what we will utilize during these challenges. If you have questions about any of these challenges, feel free to ping **Monica Miller** on the [Trino Slack](https://trino.io/slack.html), and I will be happy to answer them!

## Prerequisites

In order to use this repository you need to have [Docker](https://www.docker.com/why-docker) installed to run your service [containers](https://www.docker.com/why-docker). Check if you have Docker installed by running `docker --version`. If Docker isn't found, please refer to the [install insructions](https://docs.docker.com/engine/install/) and install Docker before trying to run these tutorials. If you're on mac or windows, you will just need to install docker desktop. If you're on a linux distribution, you will just need to install the docker engine.
