# Insight: find political donors 


Note: This code needs Python 3 to run (I use a statistics package).  This is already specified in the run.sh.  I run the 'run_tests.sh' in the test_suite, and everything works perfectly.


To solve this exercise, I use Python because it is easy to use and is able to process data in a scalable fashion.

My approach is read the file in line by line and store the information in two Python dictionaries: one for the zip code information and one for the date information.  

For the zip code dictionary, the key is the tuple (CMTE_ID,ZIP_CODE).  Then the value is a list of TRANSACTION_AMTs connected to this ID and ZIP. This way it is easy to determine if an ID and ZIP combination have already appeared, and collect the information together.  The output file is written line by line, as the lines of input are read in.

For the date dictionary, the key is the tuple (CMTE_ID,TRANSACTION_DT).  Then the value is a list of TRANSACTION_AMTs connected to this ID and ZIP. As before, the ID and Date combination are easily found, and the necessary information stored efficiently.  The output file is not written until all the lines of the input file have been read.  Then the dictionary is sorted (by its key) which is by ID, then by Date, and write the lines in this order.

I added some tests in the test_suite folder for the various input file considerations, and also created some 'tests' in the src folder, including larger input files to test the speed of the code as I was developing and experimenting with different approaches.