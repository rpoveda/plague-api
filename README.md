plague-api
==========
Plague Social Platform NodeJS API

set(options)
----------------------
Set Plague Api Options
#### Parameters:
**options:** Use this to set your latitude & longitude.
#### Sample Code:
```javascript
var plague = require('plague-api').set({
  latitude: -99.999999999999,
  longitude: -99.999999999999
});
```

login(email, password, callback)
--------------------
Login to get UserId and Token
#### Parameters:
**email:** Your plague user email.<br>
**password:** Your plague user password.<br>
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  console.log(user);
});
```

getPosts(callback)
----------------------
Return all user posts
#### Parameters:
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  //List all user posts
  plague.getPosts(function(res){
    var posts = res.posts;
    posts.forEach(function(post) {
      console.log(post);
    })
  });
});
```

getInfectionsNearby(callback)
----------------------
Return Nearby Plagues
#### Parameters:
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  plague.getInfectionsNearby(function(res){
    console.log(res);
  });
});
```

postText(text, callback)
----------------------
Send a text only post to Plague API
#### Parameters:
**text:** Text of the post.<br>
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  plague.postText('Hello Plague', function(res){
    console.log(res);
  });
});
```

postLink(mediaLink, mediaLinkPreview, text, callback)
----------------------
Send a post with a Media Link
#### Parameters:
**mediaLink:** Url of the image should be around **600x600** pixels.<br>
**mediaLinkPreview:** Url of the image should be around **300x300** pixels.<br>
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  plague.postLink(
    'http://domain.com/imageFull.png',
    'http://domain.com/imageSmall.png',
    'Hello! =)',function(res){
      console.log(res);
    });
});
```

deletePost(postId, callback)
----------------------
Delete a post using postId
#### Parameters:
**postId:** This is the id returned from **getPosts**.<br>
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  plague.deletePost(123456,function(res){
    console.log(res);
  });
});
```

deleteAllPosts(postId, callback)
----------------------
Delete all user posts
#### Parameters:
**callback:** callback function.
#### Sample Code:
```javascript
plague.login('sample@domain.com', 'mypassword', function(user){
  if(user.error){
    console.log(user.error);
    return;
  }
  plague.deleteAllPosts(function(res){
    console.log(res);
  });
});
```
