# Test1
Testing first repository

# graphql query from github :
1. Normal Query :

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

2. Query with parameter :

query getMyProfileInformation($isOwner: Boolean) {
  viewer {
    login
    name
    starredRepositories(ownedByViewer: $isOwner, first: 5) {
      nodes {
        id
        name
      }
    }
  }
}

With Query parameter :
{
  "isOwner": true
}

# ---------------------------------------------------------------------------------------------------

