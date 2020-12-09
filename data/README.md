# Data: face counts

For each appID, I stored the number of detected faces:
-   with `dlib`:
    - applied to 300x450 images: `app_ids_with_faces_with_dlib.json`
    - applied to 256x256 images: `app_ids_with_faces_with_dlib_resized.json`
-   with `face_alignment` and BGR input (this is the right way to use the module):
    - applied to 300x450 images: `app_ids_with_faces_with_fa_BGR.json`
    - applied to 256x256 images: `app_ids_with_faces_with_fa_BGR_resized.json`
-   with `face_alignment` and RBG input (this is a wrong way to use the module):
    - applied to 300x450 images: `app_ids_with_faces_with_fa_RGB.json`
    - applied to 256x256 images: `app_ids_with_faces_with_fa_RGB_resized.json`
-   with `retinaface`:
    - applied to 300x450 images: `app_ids_with_faces_with_retinaface.json`
    - applied to 256x256 images: `app_ids_with_faces_with_retinaface_resized.json`

NB: detection results obtained with bounding-boxes and face landmarks are identical.
If you only need to count faces, it is sufficient to find bounding-boxes, there is no need for face landmarks.

