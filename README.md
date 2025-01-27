# Video Doorbell, Lab 7

*A lab report by Ryan Curtis*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.**
[Link to Video](https://youtu.be/vBE619T8RDQ)

## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**
The differences are that pictureServer.js has a section to configure the webcam settings and has a section to take the picture when that message is sent in the socket.

**b. Include a video of your working video doorbell**
[Link to Video](https://youtu.be/RJi8wEaNR-Q)

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**
I tried to incorporate the node-webcam library to be able to use the bitmap representation of the image and then apply a filter to tint the image blue or red by changing all the rgb values but was unsuccessful. I then used the jimp JavaScript Image Manipulation library (https://www.npmjs.com/package/jimp) to edit the picture by applying a sepia filter to the image after it was captured but before it was loaded using the following code segment:
```
Jimp.read('public/'+imageName+'.jpg')
      .then(image =>{
        image.sepia();
        image.write('public/'+imageName+'.jpg');
});
```
However, because of the poor quality of the camera it is hard to fully see the sepia effect in the images :(

**b. Upload a video of your working modified project**
[Link to Video](https://youtu.be/qUHB-RzdUWQ)
