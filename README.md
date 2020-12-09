# java grpc bin


## Motivation
see https://github.com/ianoc/protobuf_bin

This is to add the capability to work with java grpc without needing to compile protobuf!

# Bump version:

1. Use coursier to figure out what version of protobuf you need.

```
coursier resolve --tree io.grpc:grpc-protobuf:1.27.2
└─ io.grpc:grpc-protobuf:1.27.2
   ├─ com.google.api.grpc:proto-google-common-protos:1.17.0
   ├─ com.google.guava:guava:28.1-android
   │  ├─ com.google.guava:failureaccess:1.0.1
   │  ├─ com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava
   │  ├─ com.google.j2objc:j2objc-annotations:1.3
   │  └─ org.checkerframework:checker-compat-qual:2.5.5
   ├─ com.google.protobuf:protobuf-java:3.11.0           <----- THIS ONE
   ├─ io.grpc:grpc-api:1.27.2
   │  ├─ com.google.code.findbugs:jsr305:3.0.2
   │  ├─ com.google.errorprone:error_prone_annotations:2.3.4
   │  ├─ com.google.guava:guava:28.1-android
   │  │  ├─ com.google.guava:failureaccess:1.0.1
   │  │  ├─ com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava
   │  │  ├─ com.google.j2objc:j2objc-annotations:1.3
   │  │  └─ org.checkerframework:checker-compat-qual:2.5.5
   │  ├─ io.grpc:grpc-context:1.27.2
   │  └─ org.codehaus.mojo:animal-sniffer-annotations:1.18
   └─ io.grpc:grpc-protobuf-lite:1.27.2
      ├─ com.google.guava:guava:28.1-android
      │  ├─ com.google.guava:failureaccess:1.0.1
      │  ├─ com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava
      │  ├─ com.google.j2objc:j2objc-annotations:1.3
      │  └─ org.checkerframework:checker-compat-qual:2.5.5
      └─ io.grpc:grpc-api:1.27.2
         ├─ com.google.code.findbugs:jsr305:3.0.2
         ├─ com.google.errorprone:error_prone_annotations:2.3.4
         ├─ com.google.guava:guava:28.1-android
         │  ├─ com.google.guava:failureaccess:1.0.1
         │  ├─ com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava
         │  ├─ com.google.j2objc:j2objc-annotations:1.3
         │  └─ org.checkerframework:checker-compat-qual:2.5.5
         ├─ io.grpc:grpc-context:1.27.2
         └─ org.codehaus.mojo:animal-sniffer-annotations:1.18
```

2. Go to [grpc-java](https://github.com/grpc/grpc-java) and [protobuf](https://github.com/protocolbuffers/protobuf) and look at the tags to figure out the SHAs for those versions.
3. Bump the SHAs in `.github/workflows/release.yaml`
4. Github will run the build based on the rules in `.github/workflows/release.yaml`. It's only enabled for certain branches.