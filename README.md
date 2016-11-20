# Twitchy-Gopher
A golang client library for Twitch. Aiming to support V5 of the API and video uploading.

![The Twitchy Gopher](https://raw.githubusercontent.com/ollieparsley/twitchy-gopher/master/twitchy-gopher.png)

# Installing

```
go get -u github.com/ollieparsley/twitchy-gopher
```

# Usage
This example is just to get a session. From a session you can make requests to the Twitch API.

```
package main

import (
    "fmt"

    "github.com/ollieparsley/twitchy-gopher/twitch"
)

func main() {
	// Create a new session
    sess, err := twitch.NewSession()
    if err != nil {
        panic(err)
    }

    // Create new client from the session
    t := sess.NewClient()

    // Make requests like this
    videoResp, videoErr := t.GetVideos(&t.GetVideosInput{})
    if videoErr != nil {
        panic(videoErr)
    }

}
```

# License
This SDK is distributed under the MIT License. See LICENSE for more information.

# Logo
The original gopher created by Takuya Ueda (https://twitter.com/tenntenn). Licensed under the Creative Commons 3.0 Attributions license.
