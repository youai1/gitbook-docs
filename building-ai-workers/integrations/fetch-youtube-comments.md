---
description: Fetch all comments from a YouTube video in a MindStudio workflow
---

# Fetch YouTube Comments

## Sample Output - Plain Text

```json
@user-a1b2c: Lorem ipsum dolor sit amet, consectetur adipiscing elit.

@user-d3e4f: Nulla facilisi. Sed euismod, velit vel bibendum bibendum.

@user-g5h6i: Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.

@user-j7k8l: Praesent eget nisl a massa viverra condimentum.

@user-m9n0o: Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh.

@user-p1q2r: Maecenas sed diam eget risus varius blandit sit amet non magna.

@user-s3t4u: Donec ullamcorper nulla non metus auctor fringilla.

@user-v5w6x: Cras mattis consectetur purus sit amet fermentum.

@user-y7z8a: Nullam quis risus eget urna mollis ornare vel eu leo.

@user-b9c0d: Cum sociis natoque penatibus et magnis dis parturient montes.

@user-e1f2g: Aenean lacinia bibendum nulla sed consectetur.

@user-h3i4j: Etiam porta sem malesuada magna mollis euismod.

@user-k5l6m: Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh.

@user-n7o8p: Maecenas faucibus mollis interdum.

@user-q9r0s: Sed posuere consectetur est at lobortis.

@user-t1u2v: Cum sociis natoque penatibus et magnis dis parturient montes.

@user-w3x4y: Integer posuere erat a ante venenatis dapibus posuere velit aliquet.

@user-z5a6b: Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.
```

## Sample Output - JSON

```json
[
    {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "link": "https://www.youtube.com/watch?v=example-link",
        "published_date": "2 years ago",
        "text": "Sample comment text",
        "likes": 41,
        "author": "John Doe",
        "authorLink": "https://www.youtube.com/@example-channel",
        "authorImg": "https://example.com/profile-image.jpg"
    }
]
```
