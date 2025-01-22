mkdir -p build
(
	BASEDIR=$PWD
	cd build || exit
	cmake \
		-DWITH_SYSTEM_PROVIDED_3PARTY=yes \
		-DBUILD_SHARED_LIBS=off \
		-DUNITY_DISABLE=1 \
		-DTEST_DATA_REPO_URL="${BASEDIR}/world_feed_integration_tests_data" \
		"${BASEDIR}"
)
protoc --cpp_out=. indexer/drules_struct.proto
make -C build -j$(nproc)
