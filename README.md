# Face Tracking using ARKit and Vision framework

# Compatibility

ARKit requires an iOS device with an A9 or later processor.
Vision framework requires an iOS 11 and above

# Basic Impelentation

1. Add ARSCNView to your controller
2. Create Confguration 
   ```
      let configuration = ARWorldTrackingConfiguration()
      configuration.planeDetection = .horizontal // flat surface in camera captured images
   ```
3. Add Configuration to SceneView session and Run session
4. Now Add Camera usage description Privacy key in Info.plist

After Implementation above 4 steps you can Run and check the output will be Device camera session

5. Now set sesion delegate to track AR Session behaviour 
  For eg: Session interrupted, Resumed, failed 
 


        
Version: 1.0


