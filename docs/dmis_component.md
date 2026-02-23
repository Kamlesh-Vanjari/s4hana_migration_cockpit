DMIS 2011_1_731 Installation Guide

Applies to: SAP NetWeaver 7.5 (SAP_BASIS 750, e.g., EHP8)

**1. Overview**

The DMIS 2011_1_731 add-on enables SAP Landscape Transformation (SLT) and data replication capabilities.

Supported SAP_BASIS Releases

SAP_BASIS 731 (minimum)

SAP_BASIS 740

SAP_BASIS 750

SAP_BASIS 751

SAP_BASIS 752

✔ Compatible with SAP_BASIS 750 SP13 (NW 7.5 EHP8)

2. Prerequisites
2.1 Update SPAM/SAINT

Ensure the latest SPAM/SAINT version is installed.

Check:

SPAM → Utilities → Version
2.2 Implement Required SAP Notes

Implement the following SAP Notes before installation:

1487337

1497003

1582870

1601030

1743483

1801585

Use transaction:

SNOTE
2.3 Check for Migration Workbench Components (MWB)

DMIS installation fails if CNV_* components exist.

Check:

SPAM → Utilities → Version → Component Info

If present:

Follow SAP Note 638258

Obtain deletion transport

2.4 Verify Transport Tools
SPAM → Utilities → Check → Transport Tool

Ensure:

tp and R3trans are up to date

No red errors

2.5 Verify Dictionary Consistency
SPAM → Utilities → Check → Dictionary Consistency

Resolve any errors before proceeding.

**3. Download Required Files**

Download from SAP Support Portal:

Component: DMIS 2011_1_731
Package file:

CSR0120031469_0058080.PAT
(SAPK-116AGINDMIS)
**4. Load DMIS Package**

Place the .PAT file on application server or local machine.

Go to:

SPAM → Support Package → Load Packages → From Application Server

Confirm the package appears in the queue.

**5. Install DMIS Add-On**
Step-by-Step

1️⃣ Start transaction:

SAINT

2️⃣ Click Start

3️⃣ Select:

Add-On DMIS 2011_1

4️⃣ Click Continue

5️⃣ Enter SAINT password when prompted:

51055C245A

6️⃣ Continue installation.

The system will:

Import required objects

Install dependent support packages automatically

**6. Special Notes During Installation**
BW Systems

If SAP BW is installed, you may see:

warning about open data extraction orders (CHECK_REQUIREMENTS)

✔ This warning can be safely ignored.

7. Post-Installation Verification
7.1 Confirm Component Installation
SPAM → Utilities → Version → Component Info

Verify:

DMIS 2011_1_731 installed
7.2 Check System Logs

Review for errors:

ST22  → dumps
SM21  → system log
SLG1  → application log
**8. Language Support**

DMIS includes:

German

English

French

Japanese

Additional languages can be installed later.
See SAP Note 195442.

**9. Troubleshooting**
RC = 8 during TEST_IMPORT

**Check:**

SPAM level

tp & R3trans versions

Dictionary consistency

RC = 12 during IMPORT_OBJECT_LIST

**Check:**

Missing SAP Notes

CNV_* components present

DDIC inconsistencies

Tablespace/database errors

Kernel mismatch

**Logs to review:**

/usr/sap/trans/log/SLOG*
/usr/sap/trans/log/ALOG*
10. Validation Checklist

**Before installation:**

✔ SPAM/SAINT updated
✔ Required SAP Notes implemented
✔ No CNV_* components present
✔ Transport tools up to date
✔ Dictionary consistent
✔ DMIS package loaded

**After installation:**

✔ DMIS component visible
✔ No dumps or activation errors

**11. Summary**

DMIS 2011_1_731 can be safely installed on SAP NetWeaver 7.5 systems (SAP_BASIS 750) when prerequisites are met. Ensuring SAP Notes implementation, SPAM updates, and system consistency will help the installation complete successfully.
