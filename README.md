Project Setup
-------------

### Requirements

*   Node.js (v14+ recommended)
*   Redis Server

### Installation Steps

1.  Install project dependencies:
    
    npm install
    
2.  Create a `.env` file and define the following environment variables:
    
    REDIS\_HOST=localhost
                REDIS\_PORT=6379
    REDIS\_PASSWORD=
    
    Start the Apollo Server:
    npm start
    
    Project Structure
    -----------------
    
        *   `server.js`: Main file where the Apollo Server is initialized.
        *   `pubsub.js`: File managing PubSub subscriptions via Redis.
        *   `data.js`: File containing sample data for users, posts, and comments.
        *   `resolvers.js`: File resolving GraphQL queries and mutations.
        *   `typeDefs.js`: File defining the GraphQL schema.
    
    Data Structure
    --------------
    
    ### Users
    
        
    
    Field
    
    Description
    
        
    
    id
    
    User ID
    
        
    
    fullName
    
    Full name of the user
    
        
    
    age
    
    Age of the user
    
    ### Posts
    
        
    
    Field
    
    Description
    
        
    
    id
    
    Post ID
    
        
    
    title
    
    Post title
    
        
    
    user\_id
    
    ID of the user who created the post
    
    ### Comments
    
        
    
    Field
    
    Description
    
        
    
    id
    
    Comment ID
    
        
    
    text
    
    Comment content
    
        
    
    post\_id
    
    ID of the post the comment belongs to
    
        
    
    user\_id
    
    ID of the user who made the comment
    
    Real-Time Subscriptions
    -----------------------
    
    Thanks to the Redis PubSub mechanism, it is possible to listen for specific events and receive notifications. Subscriptions allow tracking new comments, posts, or user additions.
    
    ### Example subscription request:
    
    subscription {
      newComment {
        id
        text
        post\_id
        user\_id
      }
    }
    
    License
    -------
    
    This project is open-source and protected under the MIT license.
