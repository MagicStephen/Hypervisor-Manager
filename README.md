# Hypervisor Manager

Hypervisor Manager is a full-stack web application for centralized management of virtual machines across multiple virtualization platforms.

It provides a unified interface for managing **Proxmox, VMware ESXi, KVM and Xen**, eliminating the need to work with a separate management tool for each platform.

## Key Features

* Connect and manage multiple virtualization servers
* Browse clusters, nodes and virtual machines
* Create and configure virtual machines
* Start, stop, restart and delete virtual machines
* Monitor CPU, memory, disk and network usage
* Manage VM snapshots and backups
* Access virtual machines through VNC, WebMKS and terminal consoles
* Manage node storage and upload virtual disk images
* Schedule and execute automated VM tasks
* Access management functions through a web interface or SSH CLI
* Secure authentication using JWT, password hashing and encrypted credentials

## Supported Platforms

* Proxmox VE
* VMware ESXi / vSphere
* KVM / libvirt
* Xen

## Technology Stack

### Frontend

* React
* JavaScript and JSX
* React Router
* React Bootstrap and Bootstrap 5
* Recharts
* xterm.js
* noVNC
* VMware WebMKS

### Backend

* Python
* FastAPI
* Uvicorn
* SQLAlchemy
* SQLite
* APScheduler
* AsyncSSH
* REST API and WebSockets

### Hypervisor Integration

* Proxmox REST API
* VMware vSphere API using pyVmomi
* KVM using libvirt
* Xen JSON-RPC API

### Security

* JWT authentication
* bcrypt password hashing
* Fernet credential encryption
* Short-lived console access tokens

### Documentation

* MkDocs
* Material for MkDocs
* mkdocstrings

## Architecture

The application consists of two main parts:

* A **React frontend** providing the management interface
* A **FastAPI backend** containing the business logic, security, persistence and hypervisor integrations

The backend uses a common platform abstraction layer. Each supported hypervisor has its own adapter for connections, clusters, nodes and virtual machines while exposing a consistent API to the frontend.
