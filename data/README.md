# Data: face counts

For each appID, I stored the number of detected faces:
-   with `dlib`:
    - applied to 300x450 images: `app_ids_with_faces_with_dlib.json`
    - applied to 256x256 images: `app_ids_with_faces_with_dlib_resized.json`
-   with `face_alignment`'s detection of faces (with bounding-boxes):
    - applied to 300x450 images: `app_ids_with_faces_with_fa.json`
    - applied to 256x256 images: `app_ids_with_faces_with_fa_resized.json`
-   with `face_alignment`'s prediction of face landmarks:
    - applied to 300x450 images: `refined_app_ids_with_faces_with_fa.json`
    - applied to 256x256 images: `refined_app_ids_with_faces_with_fa_resized.json`

NB: for `dlib`, detection results obtained with bounding-boxes and face landmarks are identical.
