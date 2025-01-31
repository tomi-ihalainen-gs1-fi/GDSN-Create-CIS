# Create GDSN CIS messages

Program to create GDSN Catalogue Item Subscription (CIS) messages for a data recipient based on a list of supplier GLNS.

**Background**

The CIS message is used by a data recipient create a subscription for the data of a certain supplier. The data recipient will receive
data if a publication from the supplier is in place.

More information about Global Data Synchronisation Network (GDSN): https://www.gs1.org/services/gdsn

**Usage**
1. Create a csv file in the input directory with the structure:

> gln_dr,gln_ds,tm

> 8710626000002,8719333002682,528

> gln_dr = GLN Data recipient

> gln_ds = GLN Data source

> tm = target_market

2. Change (if needed) the data_pool_gln in the source code

3. Run the program from the command prompt with the name of the csv-file as parameter

> create_cis.py test_file

4. In the directory output a new directory will be created with the same name as the csv file.
   In the created directory there a one or more batches with CIS messages. The batchsize can be changed in the source code.
   
5. Upload the xml files via FTP or AS2 to your GDSN data pool.

6. Messages will be processed by the datapool.

7. If a publication exits data will be received.
