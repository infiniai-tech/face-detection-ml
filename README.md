# face-detection-ml
Computer Vision model for Face Detection

###  Face Detection

<hr>

<p align="center">
  <img width="640" height="360" src="https://github.com/infiniai-tech/infiniai/blob/main/Results/facedetection.png">
</p>

<pre>
from infiniai.FaceDetectionModule import FaceDetector
import cv2
import time

cap = cv2.VideoCapture(0)
pTime = 0
detector = FaceDetector( )
while True:
    success, img = cap.read( )
    img, bboxs = detector.findFaces(img)
    print(bboxs)
    cTime = time.time( )
    fps = 1 / (cTime - pTime)
    pTime = cTime
    cv2.putText(img, f'FPS: {int(fps)}', (20, 70), cv2.FONT_HERSHEY_PLAIN, 5, (0, 255, 0), 5)

    cv2.imshow("Image", img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

</pre>

<hr>
