# Steam Face Detection

<img alt="Input" src="https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/cover-input.jpg" width="375"> -> <img alt="Output" src="https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/cover-output.jpg" width="375">

This repository contains Python code to detect faces on Steam store/library images.

## Usage

-   Acquire the data, e.g. as a snapshot called `256x256.zip` in [my data repository][data-repository],
-   Run [`detect_faces_on_steam_banners.ipynb`][colab-notebook-face-detection] to detect (and count) faces.
[![Open In Colab][colab-badge]][colab-notebook-face-detection]

## Data

The dataset consists of 14k vertical images, resized from 300x450 to 256x256 resolution, used by the Steam library.

Images were downloaded with [`download_steam_banners.ipynb`][download_steam_banners].
[![Open In Colab][colab-badge]][download_steam_banners]

Images were then filtered (duplicates, outliers, etc.) with [`remove_duplicates.ipynb`][filter_steam_banners].
[![Open In Colab][colab-badge]][filter_steam_banners]

## Recommendations

I have used two tools for face detection:
-   [`dlib`][dlib-github], which I used in [another one][stylegan2-projecting-images] of my projects,
-   [`face-alignment`][python-face-alignment].

Overall, I would recommend to use `face-alignment` as:
-   it detects more faces on Steam images, which feature difficult faces (hand-drawings, anime, 3D models, etc.),
-   it is about 3.5 times faster.

## Results

Overall, most images do not feature any detected face.
Among images with faces, most images feature a single face.
The more detected faces, the fewer images.

![Distribution of the number of detected faces][wiki-histogram]

Here are a few face detection results:

![Character creator][wiki-creator] ![The Sims][wiki-sims]

![Peaky Blinders][wiki-peakyblinders] ![Event D][wiki-eventD]

Keep in mind that the algorithm is not foolproof!

![Anime][wiki-anime] ![Failures][wiki-failures]

## References

-   To download images: [`download_steam_banners.ipynb`][download_steam_banners] in [`woctezuma/google-colab`][code]
-   To filter out duplicates, etc.:
    - for PNG logos: `remove_duplicates.ipynb` in [`woctezuma/google-colab`][code]
    - for JPG banners: `remove_duplicates.ipynb` in [`woctezuma/steam-stylegan2-ada`][code-ada]
-   Data stored on Google Drive: [`woctezuma/download-steam-banners-data`][images]
-   Python package for face detection: [`face-alignment`][python-face-alignment]

<!-- Definitions -->

[wiki-cover-input]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/cover-input.jpg>
[wiki-cover-output]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/cover-output.jpg>

[data-repository]: <https://github.com/woctezuma/download-steam-banners-data>
[colab-badge]: <https://colab.research.google.com/assets/colab-badge.svg>
[colab-notebook-face-detection]: <https://colab.research.google.com/github/woctezuma/steam-face-detection/blob/main/detect_faces_on_steam_banners.ipynb>

[download_steam_banners]: <https://colab.research.google.com/github/woctezuma/google-colab/blob/master/download_steam_banners.ipynb>
[filter_steam_banners]: <https://colab.research.google.com/github/woctezuma/steam-stylegan2-ada/blob/main/remove_duplicates.ipynb>

[dlib-github]: <https://github.com/davisking/dlib>
[stylegan2-projecting-images]: <https://github.com/woctezuma/stylegan2-projecting-images>
[python-face-alignment]: <https://github.com/1adrianb/face-alignment>

[wiki-histogram]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/histogram.jpg>

[wiki-creator]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/character-creator.jpg>
[wiki-sims]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/sims.jpg>

[wiki-peakyblinders]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/peaky.jpg>
[wiki-eventD]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/eventd.jpg>

[wiki-anime]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/anime.jpg>
[wiki-failures]: <https://raw.githubusercontent.com/wiki/woctezuma/steam-face-detection/img/failures.jpg>

[code]: <https://github.com/woctezuma/google-colab>
[code-ada]: <https://github.com/woctezuma/steam-stylegan2-ada>
[images]: <https://github.com/woctezuma/download-steam-banners-data>
