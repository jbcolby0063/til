# Promise

```promise``` is like committing to do something. 

If the ```promise``` is completed, it returns "resolved". But if the ```promise``` is failed, it returns "rejected".

The return value from "resolved" goes to ```then()```, and the return value from "rejected" goes to ```catch()```

```JavaScript
const userHistoryLike = false
const userMathLike = false


function userSubject() {
    return new Promise((resolve, reject) => { 
        if (userHistoryLike) {
            resolve("User likes history") // if userHistoryLike is true, it goes to .then() below
        }
        else if (userMathLike) {
            resolve("User Likes math") // if userMathLike is true, it goes to .then() below
        }
        else {
            reject({ // if both userHistoryLike and userMathLike are false, then this goes to .catch() below
                subject: "English",
                message: "User doesn't like history and math."
            })
        }
    })
}

userSubject().then((message) => {
    console.log(message)
}).catch((info) => {
    console.log(info.message + " User likes " + info.subject) // User doesn't like history and math. User likes English
})
```
