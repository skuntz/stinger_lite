set(sources
  src/adamic_adar.c
  src/betweenness.c
  src/bfs.c
  src/clustering.c
  src/community_on_demand.c
  src/kcore.c
  src/pagerank.c
  src/random.c
  src/rmat.c
  src/static_components.c
  src/weakly_connected_components.c
  # Uses structs from stinger_net
  #src/streaming_connected_components.c
  src/shortest_paths.cpp
  src/diameter.cpp
  src/independent_sets.c
  src/graph_partition.c
  src/hits_centrality.c
  src/diameter.cpp
  src/independent_sets.c
  src/graph_partition.c
  src/hits_centrality.c
  src/modularity.c
)
set(headers
  inc/adamic_adar.h
  inc/betweenness.h
  inc/bfs.h
  inc/clustering.h
  inc/community_on_demand.h
  inc/kcore.h
  inc/pagerank.h
  inc/random.h
  inc/rmat.h
  inc/static_components.h
  inc/weakly_connected_components.h
  # Uses structs from stinger_net
  #inc/streaming_connected_components.h
  inc/shortest_paths.h
  inc/diameter.h
  inc/independent_sets.h
  inc/graph_partition.h
  inc/hits_centrality.h
  inc/graph_partition.h
  inc/hits_centrality.h
  inc/modularity.h
)

publish_headers(headers "${CMAKE_BINARY_DIR}/include/stinger_alg")

include_directories("${CMAKE_BINARY_DIR}/include/stinger_alg")
include_directories("${CMAKE_BINARY_DIR}/include/stinger_core")

add_library(stinger_alg ${sources} ${headers} ${config})
target_link_libraries(stinger_alg stinger_core compat)
