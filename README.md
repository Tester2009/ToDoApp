# ToDoApp

This is a repository, for my own learning purpose. It contains a ReactJS web application that interact as FrontEnd or User Interface, Python Flask API as a Backend, and Nginx LoadBalancer as intermediary communication between FrontEnd and Backend, and lastly, MongoDB as a database.


## To run


### Requirements

- Docker
- Operating System

## Steps

1. Go ahead and clone this repository.
    > git clone https://github.com/Tester2009/ToDoApp

2. Change the directory to `database`. Make a copy of `.env.backup` to `.env`
    > cp .env.backup .env

3. Fill in the details in `.env` for `database` directory.

4. Change directory to `backend`. Make a copy of `.env.backup` to `.env`.
    > cp .env.backup .env

5. Fill in the details in `.env` for `backend` directory.

6. Change the directory to `fullstack-loadbalancer`. Run the container
    > docker compose up


## Architecture

```
                 Docker | Containerized Applications                                                                                             
                ┌───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
                │                                                                                                                               │
                │                                                                    '/' GET                                                    │
                │                                                                                                                               │
                │                                                                    '/create' POST                                             │
                │                                                                                                                               │
                │                                                                    ┌───────────────────┐                                      │
                │                                                                    │                   │                                      │
                │                                                              ┌────►│ flask | backend-1 ├─────┐                                │
                │                                                              │     │                   │     │                                │
                │                                                              │     └───────────────────┘     │                                │
                │                                                              │                               │        ┌────────────────────┐  │
┌─────────┐     │  ┌────────────────────┐         ┌──────────────────────┐     │                               │        │                    │  │
│         │     │  │                    ├────────►│                      ├─────┘                               ├───────►│ MongoDB | database │  │
│ Visitor ├─────┼─►│ reactjs | frontend │         │ nginx | loadbalancer │                                     │        │                    │  │
│         │     │  │                    │◄────────┤                      ├─────┐                               │        └────────────────────┘  │
└─────────┘     │  └────────────────────┘         └──────────────────────┘     │     ┌───────────────────┐     │                                │
                │                                                              │     │                   │     │                                │
                │                                                              │     │ flask | backend-2 ├─────┘                                │
                │                                                              └────►│                   │                                      │
                │                                                                    └───────────────────┘                                      │
                │                                                                                                                               │
                │                                                                    '/update' PUT                                              │
                │                                                                                                                               │
                │                                                                    '/delete' DELETE                                           │
                │                                                                                                                               │
                └───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
                                                                                                                                                 
                                                                                                                                                 
                                                                                                                 Made by Muazzam @ Hakase        
                                                                                                                 26/06/2024                      
                                                                                                                                                 
                                                                                                                 made possible at: asciiflow.com 
```