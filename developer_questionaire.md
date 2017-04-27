
1. You are developing a simple WhatsApp-esque messaging app in ionic/Cordova -- let&rsquo;s call it &rsquo;Chatterbox&rsquo; -- to allow chatting between friends. Put together an example HTML view using AngularJS that displays chats between two people along with a form to send messages (don&rsquo;t worry about making it pretty).

```
<div ng-app="aCoolChat">
    <div ng-controller="chat">
        <div ng-repeat="message in messages">
            {{ message.username }}
            <br/>
            {{ message.data }}
        </div>
        <div>
            <form ng-submit="submit()">
                <input type="text" ng-model="messageBox">
            </form>
        </div>

    </div>
</pre>
```

2. Write a client-side function for Chatterbox that takes a photo with the user&rsquo;s phone and then uploads that file to an imaginary server.

```
$controller("takeAndUpload";,  function () {

    navigator.camera.getPicture( function onSuccess(imgURL) {


        var request = http.request({
            hostname: "imaginary.com",
            path: "path.to.server/here",
            method: "POST",
            headers: {Accept: "text/html"}
        },
            function onUploadSuccess(response) {
                console.log("Successfully uploaded! Server responded with status: ", response.statusCode);
            },
            function onUploadFail(err) {
                console.log("Sorry just took a pic, upload failed. Server responded with ", err);
            }
        );
        request.end();

    }, function onFail(err) {
        console.log("Failed to take pic, Error:", err);
    })
});
```

3. You&rsquo;re building out a NodeJS back-end server for the app to store data to the cloud. What are the architecture/components of the server you’ll need to create to handle this?

I&rsquo;ll need a router to map the requests to the correct request handlers. This could be handled by using a specific framework that has a router, middleware, and error-handling built in. Lastly you would need a method of connecting to the cloud storage like an http server. 

4. Briefly describe the file and folder structure for your NodeJS server.

I would arrange the folders based on the components/features in the app, such as messages, and users. This would mean that I could find in each folder of a specific feature it’s view, controller and model. Test files would be a separate folder but organized similarly to the source code file structure, to make it easier to find tests. Configuration of the server and extended scripts would have their own separate folders as well.

5. What testing libraries and methodologies would you use to test different parts of the app?

Popular testing libraries are Jasmine, Mocha, and Jest. Some methodologies to use with testing are: Agile development, where there are frequent sprints allocated to working on particular goals and delivering working software frequently; Extreme Programming which is like the Agile methodology and uses Test Driven development, where a test is written first to understand what is needed and then after it fails, the feature is implemented it in order to make the test pass; the waterfall method is used when a projects requirements are fully planned out and testing is made afterwards in steps in a sequential manner.

6. List 3 database tables you might need in your data model for Chatterbox.

A potential database model could have a message table, user table, and message-reply table to link multiple messages and multiple users. 

7. What is the time complexity of a function that searches chat records for a specific word/string?

This is similiar to the Knutt-Morris Algorithm used which can be in the worst case linear or O(n).
