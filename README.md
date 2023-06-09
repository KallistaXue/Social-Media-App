# Social Media Application
## Introduction 
This is a social media app where users can connect, share, and engage with the world. 
Functions includes:
- Register user account and create user profile
- Log in to user account
- Post (create/update/display/delete)
- Comment
- Like

## API (Application Programming Interface)
API documentation for the social media app, including resources and endpoints design 

### Resources 
- Users
- Posts
- Comments
- Likes

### Endpoints

#### Users

##### 1. Create a user
POST  {{base_url}}/users/user-register

###### Query Parameters
| Name          | Type   | Description                      | Required |
|---------------|--------|----------------------------------|----------|
| username      | string | The unique username of the user. | Yes      |
| first name    | string | The first name of the user.      | Yes      |
| last name     | string | The last name of the user.       | Yes      |
| email         | string | The email address of the user.   | Yes      |
| password      | string | The password of the user.        | Yes      |
| date of birth | string | format: month-date-year.         | No       |

##### 2. Log in to user account
POST  {{base_url}}/users/user-login

###### Query Parameters
| Name          | Type   | Description                      | Required |
|---------------|--------|----------------------------------|----------|
| username      | string | The username of the user.        | Yes      |
| password      | string | The password of the user.        | Yes      |

##### 3. Get user information (eg. display user information on a profile page)
GET  {{base_url}}/users/user-info/{user_id}

###### Path Variables
| Name    | Type | Description          | Required |
|---------|------|----------------------|----------|
| user_id | int  | The ID of the user.  | Yes      |

##### 4. Update user information (can apply partial updates)
PUT  {{base_url}}/users/user-update/{user_id}

###### Path Variables
| Name    | Type | Description          | Required |
|---------|------|----------------------|----------|
| user_id | int  | The ID of the user.  | Yes      |

###### Query Parameters
| Name          | Type   | Description                      | Required |
|---------------|--------|----------------------------------|----------|
| username      | string | The unique username of the user. | Yes      |
| first name    | string | The first name of the user.      | Yes      |
| last name     | string | The last name of the user.       | Yes      |
| email         | string | The email address of the user.   | Yes      |
| password      | string | The password of the user.        | Yes      |
| date of birth | string | format: month-date-year.         | Yes      |

##### 5. Delete a user
DELETE  {{base_url}}/users/user-delete/{user_id}

###### Path Variables
| Name    | Type | Description          | Required |
|---------|------|----------------------|----------|
| user_id | int  | The ID of the user.  | Yes      |



#### Posts

##### 1. Create a post
POST  {{base_url}}/posts/post-create

###### Query Parameters
| Name    | Type   | Description                      | Required |
|---------|--------|----------------------------------|----------|
| user_id | int    | The ID of the user who posts.    | Yes      |
| content | string | The content of the post.         | Yes      |

##### 2. Get a post (post display)
GET  {{base_url}}/posts/post-info/{post_id}

###### Path Variables
| Name    | Type | Description          | Required |
|---------|------|----------------------|----------|
| post_id | int  | The ID of the post.  | Yes      |

##### 3. Update a post
PUT  {{base_url}}/posts/post-update/{post_id}

###### Path Variables
| Name    | Type | Description          | Required |
|---------|------|----------------------|----------|
| post_id | int  | The ID of the post.  | Yes      |

###### Query Parameters
| Name    | Type   | Description               | Required |
|---------|--------|---------------------------|----------|
| content | string | The updated post content. | Yes      |

##### 4. Delete a post
DELETE  {{base_url}}/posts/post-delete/{post_id}

###### Path Variables
| Name    | Type | Description          | Required |
|---------|------|----------------------|----------|
| post_id | int  | The ID of the post.  | Yes      |