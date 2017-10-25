# Face Tracking using ARKit and Vision framework

## Compatibility

iOS 11 and above
ARKit requires an iOS device with an A9 or later processor.
Vision framework requires an iOS 11 and above

## Basic Impelentation

1. Add ARSCNView to your controller
2. Create Confguration 
   ```
      let configuration = ARWorldTrackingConfiguration()
      configuration.planeDetection = .horizontal // flat surface in camera captured images
   ```
3. Add Configuration to SceneView session and Run session
4. Now Add Camera usage description Privacy key in Info.plist

After Implementation above 4 steps you can Run and output will be Device camera session

5. Now set sesion delegate to track AR Session behaviour 
  For eg: Session interrupted, Resumed, failed 
 
6. When the camera session is running the **ARSCNViewDelegate's** renderer method is called for every frame in camera.
   Here by using **Vision framework**  we find faces within image.
   We used **VNDetectFaceRectanglesRequest** to find facees, it gives result of array of **VNFaceObservation** object.
   VNFaceObservation contains the bounding box i.e the coordinates of the face within given image.
7. Use resulted bounding box to crop the face image.
8. Add your **MlModel** into project and create object for the same. 
```
let model: VNCoreMLModel = try! VNCoreMLModel(for: STYLABS_Face_CNN_v1().model)
```
9. Now create **VNCoreMLRequest** with your model and use **VNImageRequestHandler** to perform your coreMl request.(Look into checkFaceInMlModel() method)
10. As a result you will get the array of **VNClassificationObservation**
11. And finally create CNNode with VNClassificationObservation identifier and the coordinates you received in step 6 and add as child node to  ARSCNView
   

        
## Version: 1.0


