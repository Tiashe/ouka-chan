You can download the compressed file from here(http://files.pushshift.io/reddit/comments/) and run the code to create the db. you will need to change the file name and file path in the code itself.

On linux we noticed that change that read file part to

for row in sys.stdin:

        row_counter += 1

        if row_counter > start_row:
                try:
                        row = json.loads(row)

instead of

for row in f:

is better since "for row in f:" doesn't work on linux.
Note: We recommend using python 3.7 or above.
