# PG-Triggers Testbed

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This GitHub repository contains a Docker image of Neo4j, a highly scalable graph database, with the APOC plugin installed. The repository demonstrates the feasibility of the proposal outlined in the "PG-Trigger" paper. Additionally, it includes a dataset representing the schema of the COVID-19 spreading model presented in the paper.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Dataset](#dataset)
- [License](#license)

## Introduction

Neo4j is a powerful graph database that offers a flexible data model and advanced querying capabilities. It is widely used for modeling and analyzing complex relationships in various domains such as social networks, recommendation systems, and disease spreading models.

The APOC plugin (Awesome Procedures on Cypher) extends Neo4j's functionality by providing a collection of useful procedures and functions. It offers additional operations and utilities that are not available out of the box, making it easier to perform complex graph operations and data manipulations.

The "PG-Trigger" paper introduces a novel approach for handling triggers in graph databases. This repository serves as a proof of concept, showcasing the implementation of the proposed approach using Neo4j with the APOC plugin.

During our tests, the APOC plugin changed a few times thanks to the effort of the Neo4j community involved in the project. In the context of the apoc.trigger some procedures changed the syntax from version 4.1 to 4.4. In this testbed we refer to the APOC version 4.4.

## Installation

To use the Neo4j Docker image with the APOC plugin, follow the instructions below:

1. Ensure that Docker is installed on your machine. You can download Docker from the official website: [https://www.docker.com/get-started](https://www.docker.com/get-started).

2. Clone this repository to your local machine or download the ZIP archive.

3. Navigate to the repository's directory.

4. Build the Docker image by running the following command:

   ```bash
   docker build -t neo4j-apoc .
   ```
    
   This command builds the Docker image using the provided Dockerfile.

5. Once the image is built, you can run the Neo4j container with the APOC plugin using the following command:

   ```bash
      docker run -p 7474:7474 -p 7687:7687 -e NEO4J_AUTH=neo4j/password --name neo4j-apoc neo4j-apoc
   ```
    This command starts the Neo4j container and exposes the default Neo4j ports (7474 for HTTP and 7687 for Bolt). The NEO4J_AUTH   environment variable sets the default username to "neo4j" and the password to "password". You can modify these values as per your requirements.

6. Access the Neo4j browser by opening http://localhost:7474 in your web browser. Use the username "neo4j" and the password you specified in the previous step to log in.

7. You are now ready to start using Neo4j with the APOC plugin!

## Usage

Once the Neo4j container is up and running, you can interact with the database using the Neo4j browser or programmatically through Neo4j drivers.

To access the Neo4j browser, open [http://localhost:7474](http://localhost:7474) in your web browser. From there, you can execute Cypher queries, create nodes and relationships, and explore the graph database.

To programmatically interact with Neo4j, you can use any Neo4j driver compatible with the Neo4j version used in the Docker image. Configure the driver to connect to `localhost:7687` with the appropriate credentials.

## Dataset

The repository includes a dataset representing the schema of the COVID-19 spreading model presented in the "PG-Trigger" paper. 

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code as per the terms of this license.
