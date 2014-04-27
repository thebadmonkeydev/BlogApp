# Blog Platform Wlakthrough

A blogging site built entirely with rails 4 for teaching and learning

## High Level Overview
>- [Setup](#setup-section)
>- [A Post ADT](#post-section)
>- [A Comment ADT](#comment-section)
>- [User Authentication/Authorization](#user-section)
>- [Social Integration (Author and Reader side)](#social-section)
>- [Blog statistics](#stats-section)
>- [Themeing](#theme-section)
>- [Support for rich content](#media-section)

*All data types will include their created_at, updated_at attributes*

<a name="setup-section"/>
### Setting up

<a name="user-section"></a>
### User Authentication/Authorization
Will be using has_secure_password to roll our own security, for less
bloat and understanding of how it works, no need for Devise

#### User Model
| Field    | Type    | Modifiers                 |
| -------- | ------- | ------------------------- |
| id       | Integer | unique, indexed           |
| username | String  | unique, indexed, presence |
| email    | String  | unique, indexed, presence, format |
| password | String  | presence, format          |
| bio      | String  |                           |
| posts    | [Post](#post-section)    |  |
| Comments | [Comment](#comment-section) |  |

#### Notes
1. authorization will be implicit for initial, could expand later (member's
area or something.

<a name="post-section"></a>
### A Post ADT and Model
Concerns: :commentable
A post is a fairly familiar concept to most people.  In the simplest since a post is composed of two elements:

| Field    | Type    | Modifiers       |
| -------- | ------- | --------------- |
| id       | Integer | unique, indexed |
| title    | String  | presence        |
| body     | String  |                 |
| short    | String  | auto            |
| views    | Integer |  |
| draft    | Boolean |  |
| comments | [Comment](#comment-section) |  |


<a name="comment-section"></a>
### A Comment ADT and Model
Concerns: :commentable
*A brief description of the Comment ADT*

| Field    | Type    | Modifiers             |
| -------- | ------- | --------------------- |
| id       | Integer | unique, indexed       |
| body     | String  | presence, length(max) |
| user     | User    |  |

<a name="stats-section"/>
### Blog Statistics
How to accurately calculate statistics with the following
considerations:

1. Page Views
2. Date of Views
3. Browser of Views
4. Region of Views

<a name="theme-section"/>
### Visual Themes
Use a CSS-based approach which requires defining a DOM 'api' with ids
and elements so that a basic set of CSS/JS files would be used to theme
the blog pages.  Create a "clear" css file that would be included at the
top of all elements, the css file is then rendered out from theme into
erb template.

<a name="social-section"/>
### Social Integration

<a name="media-section"/>
### Rich Content
*Support for embedded images and video*



### Walkthrough
1. rails new
2. git init
3. rails s
4. TDD/dev approach (rspec, initial user specs, git practices)
5. (generate user scaffold --no-test-framework)
6. 
