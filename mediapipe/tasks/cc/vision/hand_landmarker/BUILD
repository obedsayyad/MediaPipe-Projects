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

package(default_visibility = [
    "//mediapipe/tasks:internal",
])

licenses(["notice"])

cc_library(
    name = "hand_landmarks_detector_graph",
    srcs = ["hand_landmarks_detector_graph.cc"],
    deps = [
        "//mediapipe/tasks/cc/vision/hand_landmarker/proto:hand_landmarks_detector_graph_options_cc_proto",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/status:statusor",
        "//mediapipe/calculators/core:split_vector_calculator",
        "//mediapipe/calculators/core:split_vector_calculator_cc_proto",
        "//mediapipe/calculators/image:image_properties_calculator",
        "//mediapipe/calculators/tensor:inference_calculator",
        "//mediapipe/calculators/tensor:tensors_to_classification_calculator",
        "//mediapipe/calculators/tensor:tensors_to_classification_calculator_cc_proto",
        "//mediapipe/calculators/tensor:tensors_to_floats_calculator",
        "//mediapipe/calculators/tensor:tensors_to_landmarks_calculator",
        "//mediapipe/calculators/tensor:tensors_to_landmarks_calculator_cc_proto",
        "//mediapipe/calculators/util:landmark_letterbox_removal_calculator",
        "//mediapipe/calculators/util:landmark_projection_calculator",
        "//mediapipe/calculators/util:rect_transformation_calculator",
        "//mediapipe/calculators/util:rect_transformation_calculator_cc_proto",
        "//mediapipe/calculators/util:thresholding_calculator",
        "//mediapipe/calculators/util:thresholding_calculator_cc_proto",
        "//mediapipe/calculators/util:world_landmark_projection_calculator",
        "//mediapipe/framework/api2:builder",
        "//mediapipe/framework/api2:port",
        "//mediapipe/framework/formats:classification_cc_proto",
        "//mediapipe/framework/formats:image",
        "//mediapipe/framework/formats:landmark_cc_proto",
        "//mediapipe/framework/formats:rect_cc_proto",
        "//mediapipe/framework/formats:tensor",
        # TODO: move calculators in modules/hand_landmark/calculators to tasks dir.
        "//mediapipe/modules/hand_landmark/calculators:hand_landmarks_to_rect_calculator",
        "//mediapipe/tasks/cc:common",
        "//mediapipe/tasks/cc/components/utils:gate",
        "//mediapipe/tasks/cc/components:image_preprocessing",
        "//mediapipe/tasks/cc/core:model_resources",
        "//mediapipe/tasks/cc/core:model_task_graph",
        "//mediapipe/tasks/cc/core:utils",
        "//mediapipe/tasks/cc/core/proto:inference_subgraph_cc_proto",
        "//mediapipe/tasks/cc/vision/utils:image_tensor_specs",
        "//mediapipe/util:label_map_cc_proto",
        "//mediapipe/util:label_map_util",
        "//mediapipe/tasks/cc/metadata:metadata_extractor",
        "//mediapipe/tasks/metadata:metadata_schema_cc",
    ],
    alwayslink = 1,
)

# TODO: Enable this test

cc_library(
    name = "hand_landmarker_graph",
    srcs = ["hand_landmarker_graph.cc"],
    deps = [
        ":hand_landmarks_detector_graph",
        "//mediapipe/calculators/core:begin_loop_calculator",
        "//mediapipe/calculators/core:clip_vector_size_calculator_cc_proto",
        "//mediapipe/calculators/core:end_loop_calculator",
        "//mediapipe/calculators/core:gate_calculator",
        "//mediapipe/calculators/core:gate_calculator_cc_proto",
        "//mediapipe/calculators/core:pass_through_calculator",
        "//mediapipe/calculators/core:previous_loopback_calculator",
        "//mediapipe/calculators/image:image_properties_calculator",
        "//mediapipe/calculators/util:collection_has_min_size_calculator",
        "//mediapipe/calculators/util:collection_has_min_size_calculator_cc_proto",
        "//mediapipe/framework/api2:builder",
        "//mediapipe/framework/api2:port",
        "//mediapipe/framework/formats:classification_cc_proto",
        "//mediapipe/framework/formats:detection_cc_proto",
        "//mediapipe/framework/formats:image",
        "//mediapipe/framework/formats:landmark_cc_proto",
        "//mediapipe/framework/formats:rect_cc_proto",
        "//mediapipe/framework/formats:tensor",
        "//mediapipe/tasks/cc:common",
        "//mediapipe/tasks/cc/components/utils:gate",
        "//mediapipe/tasks/cc/core:model_task_graph",
        "//mediapipe/tasks/cc/core:utils",
        "//mediapipe/tasks/cc/vision/hand_detector:hand_detector_graph",
        "//mediapipe/tasks/cc/vision/hand_detector/proto:hand_detector_graph_options_cc_proto",
        "//mediapipe/tasks/cc/vision/hand_landmarker/calculators:hand_association_calculator",
        "//mediapipe/tasks/cc/vision/hand_landmarker/calculators:hand_association_calculator_cc_proto",
        "//mediapipe/tasks/cc/vision/hand_landmarker/calculators:hand_landmarks_deduplication_calculator",
        "//mediapipe/tasks/cc/vision/hand_landmarker/proto:hand_landmarker_graph_options_cc_proto",
        "//mediapipe/tasks/cc/vision/hand_landmarker/proto:hand_landmarks_detector_graph_options_cc_proto",
    ],
    alwayslink = 1,
)

# TODO: Enable this test
