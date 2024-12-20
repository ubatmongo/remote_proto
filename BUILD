# load("@rules_java//java:defs.bzl", "java_binary")
load("@bazel_gazelle//:def.bzl", "gazelle_binary")
load("@build_stack_rules_proto//rules:proto_gazelle.bzl", "DEFAULT_LANGUAGES", "proto_gazelle")

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
# gazelle:proto_language java plugin protoc-gen-grpc-java
# gazelle:proto_language java enable true
# gazelle:proto_plugin java implementation builtin:java
# gazelle:proto_language java rule proto_compile
# gazelle:proto_plugin grpc_java implementation grpc:grpc:java

# gazelle:proto_rule proto_java_library implementation stackb:rules_proto:proto_java_library
# gazelle:proto_rule proto_java_library deps @com_google_protobuf//:protobuf
# gazelle:proto_rule proto_java_library visibility //visibility:public
# gazelle:proto_rule grpc_java_library implementation stackb:rules_proto:grpc_java_library
# gazelle:proto_rule grpc_java_library deps @com_github_grpc_grpc//:grpc++
# gazelle:proto_rule grpc_java_library deps @com_github_grpc_grpc//:grpc++_reflection
# gazelle:proto_rule grpc_java_library visibility //visibility:public

gazelle_binary(
    name = "gazelle-protobuf",
    # languages = DEFAULT_LANGUAGES,
    languages = [
        "@bazel_gazelle//language/go",
        "@bazel_gazelle//language/proto",
        # must be after the proto extension (order matters)
        "@build_stack_rules_proto//language/protobuf",
    ],
)

# proto_gazelle(
#     name = "gazelle",
#     # cfgs = ["//:config.yaml"],
#     command = "update",
#     # data = [":generated_data"],
#     gazelle = ":gazelle-protobuf",
#     imports = ["@googleapis//:imports.csv"],
# )

proto_gazelle(
    name = "gazelle",
    command = "update",
    gazelle = ":gazelle-protobuf",
)

genrule(
    name = "generated_data",
    outs = ["genfile_should_be_present_in_gazelle_data_runfiles.txt"],
    cmd = """
echo -n 'hello, world!' > $@
    """,
)
