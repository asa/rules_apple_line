# Copyright 2020 LINE Corporation
#
# LINE Corporation licenses this file to you under the Apache License,
# version 2.0 (the "License"); you may not use this file except in compliance
# with the License. You may obtain a copy of the License at:
#
#    https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
# WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
# License for the specific language governing permissions and limitations
# under the License.

load("//apple:apple_preprocessed_plist.bzl", "apple_preprocessed_plist")
load("//apple:apple_library.bzl", "apple_library")
load(
    "//examples/ios/App/Sources:constants.bzl",
    "INFO_PLIST_DICT",
)

apple_library(
    name = "Main",
    srcs = glob([
        "**/*.swift",
    ]),
    data = glob([
        "**/*.storyboard",
    ]),
    deps = [
        "//examples/ios/Mixed",
        "//examples/ios/PureObjC",
        "//examples/ios/PureSwift",
    ],
)

apple_preprocessed_plist(
    name = "PreprocessedInfoPlist",
    src = "Info.plist",
    out = "Info-Preprocessed.plist",
    substitutions = INFO_PLIST_DICT,
    visibility = ["//examples/ios/App:__pkg__"],
)

filegroup(
    name = "AppIcon",
    srcs = glob([":Assets.xcassets/AppIcon.appiconset/**"]),
    visibility = ["//visibility:public"],
)
