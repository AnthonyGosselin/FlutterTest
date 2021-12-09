# Test de camera Flutter #

Application de démonstration de control de caméra avec Flutter.
Utilisation du plugin package 'camera' de Flutter: https://pub.dev/packages/camera

Testé sur iOS.




https://user-images.githubusercontent.com/43587359/145426987-d9a1bc93-eaf1-40d7-aa7e-14d6a966190d.mp4


----------------

Code d'example de calibration de la caméra (tapper sur l'écran pour spécifier le point de calibration):

```dart
final offset = Offset(
  details.localPosition.dx / constraints.maxWidth,
  details.localPosition.dy / constraints.maxHeight,
);

cameraController.setExposurePoint(offset);
cameraController.setFocusPoint(offset);
showInSnackBar(
    "Calibration focus and exposure to (${offset.dx.toStringAsFixed(3)}, ${offset.dy.toStringAsFixed(3)})");

Future.delayed(const Duration(seconds: 2), () {
  cameraController.setFocusMode(FocusMode.locked);
  cameraController.setExposureMode(ExposureMode.locked);
  showInSnackBar("Focus and exposure locked");
});
```
(main.dart l.429)

-----------------

Source du code de référence de départ: https://github.com/flutter/plugins/blob/master/packages/camera/camera/example/lib/main.dart#L196
