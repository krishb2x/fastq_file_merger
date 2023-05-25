# fastq_file_merger
This shell script merges paired-end FASTQ files with the ".fastq.gz" extension using a specific naming convention. 
It identifies the common base name for each pair of files, merges the corresponding R1 and R2 files, and saves them with new merged file names.

Prerequisites
Unix-like environment (e.g., Linux, macOS)
Bash shell
Usage
Place the script in the directory containing the FASTQ files you want to merge.

Open a terminal and navigate to the directory where the script is located.

Make the script executable, if necessary, using the following command:


chmod +x merge_fastq.sh

Run the script using the following command:

./merge_fastq.sh

The script will identify all the files with the ".fastq.gz" extension in the current directory and its subdirectories.

After the script finishes running, the merged files will be created in the same directory with new file names based on the naming convention.

Customization

If your file naming convention differs from the script's assumptions, you can modify the script accordingly. Here's a breakdown of the different parts:

find ./ -type f -name "*.fastq.gz": This command finds all files with the ".fastq.gz" extension in the current directory and its subdirectories.

basename $F | rev | cut -c 22- | rev: This extracts the base name of each file by removing the directory path and the last 22 characters (assumed to be a specific format).

"$i"_L00*_R1_001.fastq.gz and "$i"_L00*_R2_001.fastq.gz: These are the patterns used to match and merge the R1 and R2 files, respectively. Adjust them according to your naming convention.
