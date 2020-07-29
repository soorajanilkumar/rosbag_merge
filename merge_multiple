#!/bin/bash
# script to merge multiple rosbags which are numbered in sequential order. 
# requires python script bagmerge.py in the folder
## Inputs
# start_id is the starting index of the rosbag
# end_id is the ending index of the rosbag
## Output
# Final output is stored in merge_final.bag
#
# Note:  Change the name of the starting of the rosbag in the script accordingly before execution
echo "enter the start index of the rosbags to merge"
read start_id 
echo "enter the end index of the rosbags to merge"
read end_id
echo "enter the base_name for the rosbags"
read base_name
echo "name of the output file"
read output_filename
#base_name='magni_carto_peptest'
counter=$start_id

if [ $start_id -lt $end_id ]
then
	echo "merging rosbags $start_id to $end_id"
	python bagmerge.py -o merge_$counter.bag $base_name*_$counter.bag $base_name*_$((counter+1)).bag
	((counter++))
else
	echo "error: start_id not less than end_id"
	exit 1
fi


while [ $counter -lt $end_id ]
do
	python bagmerge.py -o merge_$counter.bag merge_$((counter-1)).bag $base_name*_$((counter+1)).bag
	rm merge_$((counter-1)).bag
	((counter++))
done

mv merge_$((counter-1)).bag $output_filename.bag
echo "hope it works"
