package(default_visibility = ["//visibility:public"])

# gazelle:proto_rule proto_compile implementation stackb:rules_proto:proto_compile

# gazelle:proto_plugin cpp implementation builtin:cpp
# gazelle:proto_plugin protoc-gen-grpc-cpp implementation grpc:grpc:cpp

# gazelle:proto_rule proto_cc_library implementation stackb:rules_proto:proto_cc_library
# gazelle:proto_rule proto_cc_library deps @com_google_protobuf//:protobuf
# gazelle:proto_rule proto_cc_library visibility //visibility:public
# gazelle:proto_rule grpc_cc_library implementation stackb:rules_proto:grpc_cc_library
# gazelle:proto_rule grpc_cc_library deps @com_github_grpc_grpc//:grpc++
# gazelle:proto_rule grpc_cc_library deps @com_github_grpc_grpc//:grpc++_reflection
# gazelle:proto_rule grpc_cc_library visibility //visibility:public

# gazelle:proto_language cpp plugin cpp
# gazelle:proto_language cpp plugin protoc-gen-grpc-cpp
# gazelle:proto_language cpp rule proto_compile
# gazelle:proto_language cpp rule proto_cc_library
# gazelle:proto_language cpp rule grpc_cc_library

# gazelle:proto_language java plugin java
# gazelle:proto_language java enable true
# gazelle:proto_plugin java implementation builtin:java
# gazelle:proto_language java rule proto_compile