# Copyright 2022 The MediaPipe Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

licenses(["notice"])

package(default_visibility = ["//mediapipe/tasks:internal"])

android_library(
    name = "core",
    srcs = glob(["core/*.java"]),
    javacopts = [
        "-Xep:AndroidJdkLibsChecker:OFF",
    ],
    deps = [
        ":libmediapipe_tasks_vision_jni_lib",
        "//mediapipe/framework/formats:rect_java_proto_lite",
        "//mediapipe/java/com/google/mediapipe/framework:android_framework_no_mff",
        "//mediapipe/java/com/google/mediapipe/framework/image",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/core",
        "@maven//:com_google_guava_guava",
    ],
)

# The native library of all MediaPipe vision tasks.
cc_binary(
    name = "libmediapipe_tasks_vision_jni.so",
    linkshared = 1,
    linkstatic = 1,
    deps = [
        "//mediapipe/calculators/core:flow_limiter_calculator",
        "//mediapipe/java/com/google/mediapipe/framework/jni:mediapipe_framework_jni",
        "//mediapipe/tasks/cc/vision/gesture_recognizer:gesture_recognizer_graph",
        "//mediapipe/tasks/cc/vision/image_classifier:image_classifier_graph",
        "//mediapipe/tasks/cc/vision/object_detector:object_detector_graph",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/core/jni:model_resources_cache_jni",
    ],
)

cc_library(
    name = "libmediapipe_tasks_vision_jni_lib",
    srcs = [":libmediapipe_tasks_vision_jni.so"],
    alwayslink = 1,
)

android_library(
    name = "objectdetector",
    srcs = [
        "objectdetector/ObjectDetectionResult.java",
        "objectdetector/ObjectDetector.java",
    ],
    javacopts = [
        "-Xep:AndroidJdkLibsChecker:OFF",
    ],
    manifest = "objectdetector/AndroidManifest.xml",
    deps = [
        ":core",
        "//mediapipe/framework:calculator_options_java_proto_lite",
        "//mediapipe/framework/formats:detection_java_proto_lite",
        "//mediapipe/framework/formats:location_data_java_proto_lite",
        "//mediapipe/java/com/google/mediapipe/framework:android_framework",
        "//mediapipe/java/com/google/mediapipe/framework/image",
        "//mediapipe/tasks/cc/core/proto:base_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/object_detector/proto:object_detector_options_java_proto_lite",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:category",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:detection",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/core",
        "//third_party:autovalue",
        "@maven//:com_google_guava_guava",
    ],
)

android_library(
    name = "imageclassifier",
    srcs = [
        "imageclassifier/ImageClassificationResult.java",
        "imageclassifier/ImageClassifier.java",
    ],
    javacopts = [
        "-Xep:AndroidJdkLibsChecker:OFF",
    ],
    manifest = "imageclassifier/AndroidManifest.xml",
    deps = [
        ":core",
        "//mediapipe/framework:calculator_options_java_proto_lite",
        "//mediapipe/java/com/google/mediapipe/framework:android_framework",
        "//mediapipe/java/com/google/mediapipe/framework/image",
        "//mediapipe/tasks/cc/components/containers/proto:category_java_proto_lite",
        "//mediapipe/tasks/cc/components/containers/proto:classifications_java_proto_lite",
        "//mediapipe/tasks/cc/core/proto:base_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/image_classifier/proto:image_classifier_graph_options_java_proto_lite",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:category",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:classification_entry",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:classifications",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/processors:classifieroptions",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/core",
        "//third_party:autovalue",
        "@maven//:com_google_guava_guava",
    ],
)

android_library(
    name = "gesturerecognizer",
    srcs = [
        "gesturerecognizer/GestureRecognitionResult.java",
        "gesturerecognizer/GestureRecognizer.java",
    ],
    javacopts = [
        "-Xep:AndroidJdkLibsChecker:OFF",
    ],
    manifest = "gesturerecognizer/AndroidManifest.xml",
    deps = [
        ":core",
        "//mediapipe/framework:calculator_options_java_proto_lite",
        "//mediapipe/framework/formats:classification_java_proto_lite",
        "//mediapipe/framework/formats:landmark_java_proto_lite",
        "//mediapipe/java/com/google/mediapipe/framework:android_framework",
        "//mediapipe/java/com/google/mediapipe/framework/image",
        "//mediapipe/tasks/cc/components/processors/proto:classifier_options_java_proto_lite",
        "//mediapipe/tasks/cc/core/proto:base_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/gesture_recognizer/proto:gesture_recognizer_graph_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/gesture_recognizer/proto:hand_gesture_recognizer_graph_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/hand_detector/proto:hand_detector_graph_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/hand_landmarker/proto:hand_landmarker_graph_options_java_proto_lite",
        "//mediapipe/tasks/cc/vision/hand_landmarker/proto:hand_landmarks_detector_graph_options_java_proto_lite",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:category",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/components/containers:landmark",
        "//mediapipe/tasks/java/com/google/mediapipe/tasks/core",
        "//third_party:autovalue",
        "@maven//:com_google_guava_guava",
    ],
)
