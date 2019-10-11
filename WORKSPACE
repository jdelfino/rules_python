# Copyright 2017 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

workspace(name = "rules_python")

local_repository(
    name = "io_bazel_rules_python",
    path = ".",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")

http_archive(
    name = "bazel_federation",
    url = "https://github.com/bazelbuild/bazel-federation/releases/download/0.0.1/bazel_federation-0.0.1.tar.gz",
    sha256 = "506dfbfd74ade486ac077113f48d16835fdf6e343e1d4741552b450cfc2efb53",
)

load("@bazel_federation//:repositories.bzl", "rules_python_deps")
rules_python_deps()

load("@bazel_federation//setup:rules_python.bzl",  "rules_python_setup")
rules_python_setup(use_pip=True)

# Test data for WHL tool testing.
http_file(
    name = "grpc_whl",
    sha256 = "c232d6d168cb582e5eba8e1c0da8d64b54b041dd5ea194895a2fe76050916561",
    # From https://pypi.python.org/pypi/grpcio/1.6.0
    urls = [("https://pypi.python.org/packages/c6/28/" +
            "67651b4eabe616b27472c5518f9b2aa3f63beab8f62100b26f05ac428639/" +
            "grpcio-1.6.0-cp27-cp27m-manylinux1_i686.whl")],
)

http_file(
    name = "futures_3_1_1_whl",
    sha256 = "c4884a65654a7c45435063e14ae85280eb1f111d94e542396717ba9828c4337f",
    # From https://pypi.python.org/pypi/futures
    urls = [("https://pypi.python.org/packages/a6/1c/" +
            "72a18c8c7502ee1b38a604a5c5243aa8c2a64f4bba4e6631b1b8972235dd/" +
            "futures-3.1.1-py2-none-any.whl")],
)

http_file(
    name = "futures_2_2_0_whl",
    sha256 = "9fd22b354a4c4755ad8c7d161d93f5026aca4cfe999bd2e53168f14765c02cd6",
    # From https://pypi.python.org/pypi/futures/2.2.0
    urls = [("https://pypi.python.org/packages/d7/1d/" +
            "68874943aa37cf1c483fc61def813188473596043158faa6511c04a038b4/" +
            "futures-2.2.0-py2.py3-none-any.whl")],
)

http_file(
    name = "wheel_0_31_0_whl",
    sha256 = "9cdc8ab2cc9c3c2e2727a4b67c22881dbb0e1c503d592992594c5e131c867107",
    # From https://pypi.python.org/pypi/wheel/0.31.0
    urls = [("https://pypi.python.org/packages/1b/d2/" +
            "22cde5ea9af055f81814f9f2545f5ed8a053eb749c08d186b369959189a8/" +
            "wheel-0.31.0-py2.py3-none-any.whl")],
)

http_file(
    name = "mock_whl",
    sha256 = "5ce3c71c5545b472da17b72268978914d0252980348636840bd34a00b5cc96c1",
    # From https://pypi.python.org/pypi/mock
    urls = [("https://pypi.python.org/packages/e6/35/" +
            "f187bdf23be87092bd0f1200d43d23076cee4d0dec109f195173fd3ebc79/" +
            "mock-2.0.0-py2.py3-none-any.whl")],
)

http_file(
    name = "google_cloud_language_whl",
    sha256 = "a2dd34f0a0ebf5705dcbe34bd41199b1d0a55c4597d38ed045bd183361a561e9",
    # From https://pypi.python.org/pypi/google-cloud-language
    urls = [("https://pypi.python.org/packages/6e/86/" +
            "cae57e4802e72d9e626ee5828ed5a646cf4016b473a4a022f1038dba3460/" +
            "google_cloud_language-0.29.0-py2.py3-none-any.whl")],
)

# Everything below this line is used only for developing rules_python. Users
# should not copy it to their WORKSPACE.

load("//:internal_deps.bzl", "rules_python_internal_deps")
rules_python_internal_deps()

load("//:internal_setup.bzl", "rules_python_internal_setup")
rules_python_internal_setup()
