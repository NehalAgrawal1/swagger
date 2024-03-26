openapi: 3.0.0
info:
  title: Todo List API
  description: API for managing to-do items
  version: 1.0.0
servers:
  - url: /api
    description: Development server
paths:
  /todos:
    get:
      summary: Retrieves all to-do items
      responses:
        '200':
          description: A list of to-do items
          content:
            application/json:
              schema:
                type: object
                properties:
                  todos:
                    type: array
                    items:
                      type: object
                      properties:
                        id:
                          type: integer
                          description: The unique identifier for the to-do item
                        todo:
                          type: string
                          description: The description of the to-do item
                        completed:
                          type: boolean
                          description: Indicates whether the to-do item is completed
                      example:
                        id: 1
                        todo: Complete REST API training
                        completed: true
    post:
      summary: Adds a new to-do item
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                todo:
                  type: string
                  description: The description of the new to-do item
                completed:
                  type: boolean
                  description: Indicates whether the new to-do item is completed
              example:
                todo: Use SWAGGER in the project
                completed: false
      responses:
        '200':
          description: The newly created to-do item
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                    description: The unique identifier for the new to-do item
                  todo:
                    type: string
                    description: The description of the new to-do item
                  completed:
                    type: boolean
                    description: Indicates whether the new to-do item is completed
                example:
                  id: 151
                  todo: Use SWAGGER in the project
                  completed: false
