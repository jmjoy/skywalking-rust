# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.
#
FROM rust:1.85
RUN apt-get update && apt-get install -y cmake protobuf-compiler
RUN rustup toolchain install nightly-2025-03-24
WORKDIR /build
COPY . /build/
RUN cargo build --release --workspace
ENV RUST_BACKTRACE=1
ENTRYPOINT ["/build/target/release/e2e"]
