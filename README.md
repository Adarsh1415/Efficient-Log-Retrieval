# Efficient-Log-Retrieval
Key Steps :- 
 
1. Preprocess the input date to get the next day's date. For example, if the input is 2024-12-01, the next day is 2024-12-02.

2. Perform a binary search to find the start byte of the first log entry with the target date.

3. Perform another binary search to find the start byte of the first log entry with the next day's date.

4. Once the start and end bytes are found, read from start to end-1 and write to the output file.

**Step by Step Breakdown**

Binary Search: The binary search efficiently locates the start and end positions of the logs for the specified date by leveraging the sorted nature of the log entries. This reduces the time complexity to O(log N), where N is the file size.

File Handling: The file is read in binary mode, and operations are performed using byte offsets to handle large files without loading them into memory.

Chunk Reading: The solution reads the log entries in chunks between the identified start and end positions, ensuring efficient memory usage and quick write operations to the output file.
