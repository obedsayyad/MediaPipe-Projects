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

# Placeholder for internal Python strict test compatibility macro.

package(default_visibility = ["//mediapipe/tasks:internal"])

licenses(["notice"])

py_test(
    name = "object_detector_test",
    srcs = ["object_detector_test.py"],
    data = [
        "//mediapipe/tasks/testdata/vision:test_images",
        "//mediapipe/tasks/testdata/vision:test_models",
    ],
    deps = [
        "//mediapipe/python:_framework_bindings",
        "//mediapipe/tasks/python/components/containers:bounding_box",
        "//mediapipe/tasks/python/components/containers:category",
        "//mediapipe/tasks/python/components/containers:detections",
        "//mediapipe/tasks/python/core:base_options",
        "//mediapipe/tasks/python/test:test_utils",
        "//mediapipe/tasks/python/vision:object_detector",
        "//mediapipe/tasks/python/vision/core:vision_task_running_mode",
    ],
)
