# ORACLE PLUGGABLE DATABASES (PDB) MANANAGEMENT
## STEP 1: INSTALL ORACLE DATABASE
### Action
Installed Oracle Database 21c successfully.
### Result

<img width="1161" height="883" alt="image" src="https://github.com/user-attachments/assets/b5333c55-ce33-46c7-b49d-42f482f0cc40" />

Database services are running.
<img width="880" height="205" alt="image" src="https://github.com/user-attachments/assets/0a33a0e9-fa76-40e1-886d-86739269cdfa" />

<img width="1345" height="768" alt="image" src="https://github.com/user-attachments/assets/32649ebd-986e-48cb-a361-d3e266f332bc" />

## Step 2 – Install SQL Developer
### Action
Installed SQL Developer and opened it.
### Result
Application launches correctly.

<img width="1704" height="886" alt="image" src="https://github.com/user-attachments/assets/fb242118-63fe-403e-a00d-3b151f24303f" />

## Step 3 – Creating connection

<img width="1143" height="724" alt="image" src="https://github.com/user-attachments/assets/8a532454-be94-4672-814b-3778c8e06e50" />

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

<img width="1700" height="894" alt="image" src="https://github.com/user-attachments/assets/afa91cac-b28b-45a8-b0c4-aea3818b147c" />

ALTER PLUGGABLE DATABASE an_pdb_28453 OPEN;

ALTER PLUGGABLE DATABASE an_pdb_28453 SAVE STATE;
### Check OPEN state
SHOW PDBS;

<img width="1699" height="887" alt="image" src="https://github.com/user-attachments/assets/949cf56d-5647-462d-b342-7051cde94281" />

# Create temporary PDB
### create temporary pdb
### sql code
CREATE PLUGGABLE DATABASE an_temp_28453
ADMIN USER annick_plsqlauca_temp_28453 IDENTIFIED BY password123
FILE_NAME_CONVERT = ('pdbseed', 'an_temp_28453');

<img width="1699" height="889" alt="image" src="https://github.com/user-attachments/assets/217e8edd-8625-4787-9478-bb2504c2f5b7" />

### Open the temporary PDB
ALTER PLUGGABLE DATABASE an_temp_28453 OPEN;

SELECT NAME, OPEN_MODE FROM V$PDBS;

<img width="1699" height="886" alt="image" src="https://github.com/user-attachments/assets/3525378e-21b9-4157-91e4-027478932fd3" />

### Close the temporary PDB
ALTER PLUGGABLE DATABASE an_temp_28453 CLOSE IMMEDIATE;

### Delete the temporary PDB completely
DROP PLUGGABLE DATABASE an_temp_28453 INCLUDING DATAFILES;

<img width="1702" height="897" alt="image" src="https://github.com/user-attachments/assets/abb1bc5b-0382-4165-8184-08ea69d7ad8b" />

### Confirm it no longer exists
SELECT NAME, OPEN_MODE FROM V$PDBS;

<img width="1704" height="898" alt="image" src="https://github.com/user-attachments/assets/af40e4aa-daaf-47a6-b7a8-987b9a9e05cb" />

#  Oracle Enterprise Manager (OEM)

Configure and access Oracle Enterprise Manager (OEM)

## OEM dashboard
<img width="1903" height="825" alt="image" src="https://github.com/user-attachments/assets/78672c52-869f-4b1e-9843-e5180a111f8a" />




