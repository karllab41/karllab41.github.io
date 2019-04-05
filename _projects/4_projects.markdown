---
layout: page
title: Some Tensorflow JS
description: First attempt
img: https://upload.wikimedia.org/wikipedia/commons/thumb/5/52/SophieAndersonTakethefairfaceofWoman.jpg/220px-SophieAndersonTakethefairfaceofWoman.jpg
---

<html>
  <head>
    <!-- Load TensorFlow.js -->
    <script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@1.0.0"></script>
    <!-- Load BodyPix -->
    <script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/body-pix@1.0.0"></script>
 </head>

  <body>
    <img id='person' src='/images/person.jpg '/>
  </body>
  <!-- Place your code in the script tag below. You can also use an external .js file -->
  <script>
    var outputStride = 16;
    var segmentationThreshold = 0.5;

    var imageElement = document.getElementById('image');

    bodyPix.load().then(function(net){
      return net.estimatePersonSegmentation(imageElement, outputStride, segmentationThreshold)
    }).then(function(segmentation){
      console.log(segmentation);
    })
  </script>
</html>
