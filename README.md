# HackPrincetonF16

In the current media landscape, control over distribution has become almost as important as the actual creation of content, and that has given Facebook a huge amount of power. The impact that Facebook newsfeed has in the formation of opinions in the real world is so huge that it potentially affected the 2016 election decisions, however these newsfeed were not completely accurate. Our solution? FiB because with 1.5 Billion Users, Every Single Tweak in an Algorithm Can Make a Change, and we don't stop at just one.

##Installation
####The easy way
Go to the [chrome web store](https://chrome.google.com/webstore/detail/fib/ofpheinlpjdffpdakjegbcphdfeekpnn "Chrome Web Store") and add our extension to your browser
####The harder way
#####(For those who want the latest features)
1. Download "extension" folder from our repository
2. Go to chrome and enable developer settings.
3. Then go to your extensions page and click "add unbundled extension"
4. Find the extension where you downloaded it and select it
5. The extension should be added now

######Backend Server Docker Container
To build the backend python server locally to use with the extension, this repository includes [backend/Dockerfile](backend/Dockerfile).

Build the Docker image
```
cd backend/
docker build -t hackprincetonf16 .
```

Run the Docker container locally on port 5000
```
docker run -it --rm -p 5000:5000 hackprincetonf16
```

Update `var server` in [extension/myScript.js](extension/myScript.js) to `http://localhost:5000` before installing the extension manually.

##About us
This project is still under development (a lot of work is required and is also being put in). All of us are Univeristy students trying to help solve a problem social media faces. As university we may sometimes take a while to fix issues or approve pull request, please bear with us. We are always on the lookout for sponsors for this project as we are non-profit and need money to run our servers and cover our API costs.

##Contributing to this project
We love contributors. We are open source and every contribution helps. Please read [CONTRIBUTE.md](CONTRIBUTE.md) for how to contribute to our project.

##Licensing
This project is protected under Open Software License 3.0

Please read [License.md](License.md)

# NOTES

chrome extension: https://chrome.google.com/webstore/detail/fib/ofpheinlpjdffpdakjegbcphdfeekpnn

This extension analyzes your Facebook feed for a url, picture, and text's validitiy.
In the current media landscape, control over distribution has become almost as important as the actual creation of content, and that has given Facebook a huge amount of power. The impact that Facebook newsfeed has in the formation of opinions in the real world is so huge that it potentially affected the 2016 election decisions, however these newsfeed were not completely accurate. Our solution? FiB because With 1.5 Billion Users, Every Single Tweak in an Algorithm Can Make a Change, and we dont stop at just one.

Our algorithm is two fold, as follows:

Content-consumption: Our chrome-extension goes through your facebook feed in real time as you browse it and verifies the authenticity of posts. These posts can be status updates, images or links. Our backend AI checks the facts within these posts and verifies them using image recognition, keyword extraction, and source verification and a twitter search to verify if a screenshot of a twitter update posted is authentic. The posts then are visually tagged on the top right corner in accordance with their trust score. If a post is found to be false, the AI tries to find the truth and shows it to you.

Content-creation: Each time a user posts/shares content, our chat bot uses a webhook to get a call. This chat bot then uses the same backend AI as content consumption to determine if the new post by the user contains any unverified information. If so, the user is notified and can choose to either take it down or let it exist.
