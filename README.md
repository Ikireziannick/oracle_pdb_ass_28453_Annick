# ORACLE PLUGGABLE DATABASES (PDB) MANANAGEMENT
## STEP 1: INSTALL ORACLE DATABASE
### Action
Installed Oracle Database 21c successfully.
###Result
Database services are running.

<img width="1345" height="768" alt="image" src="https://github.com/user-attachments/assets/32649ebd-986e-48cb-a361-d3e266f332bc" />


<img width="880" height="205" alt="image" src="https://github.com/user-attachments/assets/0a33a0e9-fa76-40e1-886d-86739269cdfa" />

## Step 2 – Install SQL Developer
###Action
Installed SQL Developer and opened it.
###Result
Application launches correctly.

<img width="1704" height="886" alt="image" src="https://github.com/user-attachments/assets/fb242118-63fe-403e-a00d-3b151f24303f" />

## Step 3 – Connect as SYSDBA
### Command

conn sys as sysdba

### Result
Connected successfully with SYS privileges.

<img width="1339" height="760" alt="image" src="https://github.com/user-attachments/assets/19f098de-dab4-4a26-916c-b394c3e3e97e" />

## Step 4 – Check Current Container
### Command

SHOW CON_NAME;

### Output
CDB$ROOT

<img width="1341" height="754" alt="image" src="https://github.com/user-attachments/assets/c7e3d011-107e-40c9-a4a8-70597c7eb875" />

### Explanation
Confirmed we are inside the root container.
# CREATING A NEW PLUGGABLE DATABASE
### Sql command
CREATE PLUGGABLE DATABASE an_pdb_28453
ADMIN USER annick_plsqlauca_28453 IDENTIFIED BY password123
FILE_NAME_CONVERT = ('pdbseed', 'an_pdb_28453');
ALTER PLUGGABLE DATABASE an_pdb_28453 OPEN;
ALTER PLUGGABLE DATABASE an_pdb_28453 SAVE STATE;
### Check OPEN state
SHOW PDBS;
# Create temporary PDB
### sql code
### create temporary pdb
CREATE PLUGGABLE DATABASE an_temp_28453
ADMIN USER annick_plsqlauca_temp_28453 IDENTIFIED BY password123
FILE_NAME_CONVERT = ('pdbseed', 'an_temp_28453');
### Open the temporary PDB
ALTER PLUGGABLE DATABASE an_temp_28453 OPEN;
SELECT NAME, OPEN_MODE FROM V$PDBS;
### Close the temporary PDB
ALTER PLUGGABLE DATABASE an_temp_28453 CLOSE IMMEDIATE;
### Delete the temporary PDB completely
DROP PLUGGABLE DATABASE an_temp_28453 INCLUDING DATAFILES;
### Confirm it no longer exists
SELECT NAME, OPEN_MODE FROM V$PDBS;

