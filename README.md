# Co-location

This project is based on the "Parallel Spatial Co-location Mining Algorithm" originally implemented by Shagun Sodhani (https://github.com/shagunsodhani/locis)

## There are four MapReduce tasks run in a sequence: 

###### 1. Run Neighbour Search MapReduce task

hadoop jar target/uber-locis-0.0.1-SNAPSHOT.jar com.github.locis.apps.NeighborSearch <input_path_to_read_raw_data> <output_path_to_write_neighbors>

###### 2. run Neighbour Grouping MapReduce task

hadoop jar target/uber-locis-0.0.1-SNAPSHOT.jar com.github.locis.apps.NeighborGrouping <input_path_to_read_neighbors> <output_path_to_write_neighbor_groups>

###### 3. run Count Instance MapReduce task

hadoop jar target/uber-locis-0.0.1-SNAPSHOT.jar com.github.locis.apps.CountInstance <input_path_to_read_neighbor_groups> <output_path_to_write_instance_count>

###### 4. run Colocation Pattern Search MapReduce task

hadoop jar target/uber-locis-0.0.1-SNAPSHOT.jar com.github.locis.apps.PatternSearch <input_path_to_read_neighbor_groups> <output_path_to_write_prevalence_scores> <size_of_colocation>
