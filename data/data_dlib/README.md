# Pre-trained Models

This directory should contain the following dlib pre-trained models:

## Required Files

### 1. Shape Predictor (68 Facial Landmarks)
- **File**: `shape_predictor_68_face_landmarks.dat`
- **Download**: http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
- **Size**: ~99 MB (compressed)

### 2. Face Recognition Model (ResNet)
- **File**: `dlib_face_recognition_resnet_model_v1.dat`
- **Download**: http://dlib.net/files/dlib_face_recognition_resnet_model_v1.dat.bz2
- **Size**: ~22 MB (compressed)

## Quick Download (Linux/macOS)

```bash
# Download and extract shape predictor
wget http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
bzip2 -d shape_predictor_68_face_landmarks.dat.bz2

# Download and extract face recognition model
wget http://dlib.net/files/dlib_face_recognition_resnet_model_v1.dat.bz2
bzip2 -d dlib_face_recognition_resnet_model_v1.dat.bz2
```

## Quick Download (Windows PowerShell)

```powershell
# Download files (use browser or curl)
# Extract using 7-Zip or similar tool
```

## Directory Structure After Setup

```
data/
├── data_dlib/
│   ├── README.md (this file)
│   ├── shape_predictor_68_face_landmarks.dat
│   └── dlib_face_recognition_resnet_model_v1.dat
├── data_faces_from_camera/
│   └── (face images will be stored here)
└── features_all.csv (generated after feature extraction)
```

## Notes

- These models are provided by dlib under the Creative Commons License
- Do not upload these large files to Git repositories
- The `.gitignore` file is configured to exclude these `.dat` files
