# rosbag_merge
Helpful code to merge multiple rosbags recorded using the --split option.


## When to use it?
When we use the --split option when recording rosbags,the rosbags are saved with the format <data_stamp>_<index>.bag

Example --split usage
```
rosbag record --split --duration=1m --all
```
This will record rosbags with 1 minute duration. Very helpful to prevent corrupting the whole rosbag in case of any glitches!


## Usage
To run, go to the project location in terminal and do

```
./merge_multiple
```

If the rosbags saved are in the format <br/>
2020-07-28-13-32-41_0.bag <br/>
2020-07-28-13-33-41_1.bag <br/>
2020-07-28-13-34-41_2.bag <br/>
2020-07-28-13-35-41_3.bag <br/>

and you want to merge the rosbags <*>_1.bag,<*>_2.bag and <*>_3.bag in the directory /home/sooraj/rosbags/ ,  <br/> 
then 
```
enter the start index of the rosbags to merge
1
enter the end index of the rosbags to merge
3
enter the base_name for the rosbags
/home/sooraj/rosbags/2020-07-28-13
name of the output file
merged
```

Wait for the message `hope it works!`
