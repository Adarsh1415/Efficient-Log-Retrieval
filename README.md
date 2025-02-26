# Efficient-Log-Retrieval
Key Steps :- 
 
1. Preprocess the input date to get the next day's date. For example, if the input is 2024-12-01, the next day is 2024-12-02.

2. Perform a binary search to find the start byte of the first log entry with the target date.

3. Perform another binary search to find the start byte of the first log entry with the next day's date.

4. Once the start and end bytes are found, read from start to end-1 and write to the output file.


**Binary Search Implementation**

For finding the start of the target date:

- Initialize low = 0, high = file size.

- While low < high:

- mid = (low + high) // 2

- Seek to mid.

- Move the file pointer to the start of the next line (since mid might be in the middle of a line).

- Read the line and extract its date.

- Compare the date with the target date.

- If the line's date is earlier than the target, set low = mid + 1.

- Else, set high = mid.

- Once the loop ends, low should be the start of the first line with the target date.

Similarly, for the end position, we need to find the first line of the next day and take its position as the end.


**According to the problem statement, the logs are generated almost equally every day. So the date is likely present.**

Once we find the start of the first line with the target date, then we need to find the start of the next day's logs. Then, read from the start to the end position.

**Steps**

1. Find start_byte: the first line with target_date.

2. Find end_byte: the first line with next_day_date.

3. Read all lines from start_byte to end_byte -1.

