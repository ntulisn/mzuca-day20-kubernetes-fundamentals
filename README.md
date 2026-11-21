# Kubernetes Day 20 Lab: Deploying Pods and Deployments

## What Kubernetes Is

Kubernetes (K8s) is an open-source container orchestration platform that automates deploying, scaling, and managing containerized applications. Instead of manually running individual containers on a server, Kubernetes lets you declare the desired state of your applications using YAML manifests, and the cluster continuously works to maintain that state—restarting failed containers, scaling replicas up or down, and routing network traffic.
________________________________________

## What I Built

I configured a working container runtime environment on Ubuntu 26.04.1 LTS and deployed two foundational Kubernetes workloads running lightweight nginx:alpine web servers on port 80:
1. pod.yaml (nginx-pod): A standalone single-container Pod running Nginx.
2. deployment.yaml (web-deployment): A scalable Deployment managing 2 identical replicas of the Nginx web application.
________________________________________

## Purpose of Each Kubernetes Resource
 
	Pod (kind: Pod): The smallest deployable compute unit in Kubernetes. It wraps one or more tightly coupled containers (in this case, nginx-container) that share networking and storage resources. Standalone Pods are useful for quick testing, though they are not automatically recreated if deleted or if a node fails.

	Deployment (kind: Deployment): A higher-level controller that manages stateless applications. Rather than creating Pods directly, a Deployment defines the desired number of replicas (replicas: 2), uses label selectors (app: web-app) to track its Pods, and ensures self-healing and zero-downtime rolling updates.
________________________________________
