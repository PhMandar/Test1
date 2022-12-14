# Test1
Testing first repository

# My first graphql query from github :

query getMyProfileInformation {
  viewer {
    login
    name
    bio
    id
    following(first: 20) {
      nodes {
        ...userInfo
      }
    }
    firstFollowers: followers(first: 3) {
      nodes {
        ...userInfo
      }
    }
    lastFollowers: followers(last: 2) {
      nodes {
        ...userInfo
      }
    }
  }
}

fragment userInfo on User {
  id
  bio
  bioHTML
  avatarUrl
}

# ---------------------------------------------------------------------------------------------------
