# utl-using-proc-append-to-copy-a-dataset-with-a-new-name-in-the-same-library
Using proc append to copy a dataset with a new name in the same library
    %let pgm=utl-using-proc-append-to-copy-a-dataset-with-a-new-name-in-the-same-library;

    %stop_submission;

    Using proc append to copy a dataset with a new name in the same library

    Problem

      Copy work.have to work.want fails with proc copy

    github
    https://tinyurl.com/3pzm6yw2
    https://github.com/rogerjdeangelis/utl-using-proc-append-to-copy-a-dataset-with-a-new-name-in-the-same-library

    SOAPBOX ON

    PROC COPY cannot directly create a copy of a dataset with a new name
    in the same library in a single step. PROC COPY is designed to copy
    datasets from one library to another, but it does not
    have an option to rename datasets during the copy process.
    Syntax for proc copy

    proc copy in=work out=cannot be work;
        select dataset1 ; /*---- only one name possible ----*/
    run;

    SOAPBOX OFF

    /***********************************************************************************************************************/
    /*                    INPUT                      |     PROCESS         |              OUTPUT(clone)                    */
    /*                    =====                      |     =======         |              =============                    */
    /*  Attributes of work.have                      |                     |                                               */
    /*                                               |                     |                                               */
    /*                                               |                     |                                               */
    /* Data Set Name             WORK.HAVE           | proc datasets;      | Data Set Name            WORK.HAVE            */
    /* Member Type               DATA                |   delete want;      | Member Type              DATA                 */
    /* Engine                    V9                  | run;quit;           | Engine                   V9                   */
    /* Created                   05/17/2025 09:25:54 |                     | Created                  05/17/2025 09:25:54  */
    /* Last Modified             05/17/2025 09:25:54 | proc append         | Last Modified            05/17/2025 09:25:54  */
    /*                                               |   base = work.want  |                                               */
    /* Observations              19                  |   data = work.have; | Observations             19                   */
    /* Variables                 5                   | run;quit;           | Variables                5                    */
    /* Indexes                   0                   |                     | Indexes                  0                    */
    /* Observation Length        40                  |                     | Observation Length       40                   */
    /* Deleted Observations      0                   |                     | Deleted Observations     0                    */
    /* Compressed                NO                  |                     | Compressed               NO                   */
    /* Sorted                    NO                  |                     | Sorted                   NO                   */
    /*                                               |                     |                                               */
    /* Data Set Page Size       65536                |                     | Data Set Page Size       65536                */
    /* Number of Data Set Pages 1                    |                     | Number of Data Set Pages 1                    */
    /* First Data Page          1                    |                     | First Data Page          1                    */
    /* Max Obs per Page         1632                 |                     | Max Obs per Page         1632                 */
    /* Obs in First Data Page   19                   |                     | Obs in First Data Page   19                   */
    /*                                               |                     |                                               */
    /* ExtendObsCounter          YES                 |                     | ExtendObsCounter         YES                  */
    /* Not sure Seimens or StatTrasfer               |                     | Not sure Seimens or StatTrasfer               */
    /* supports this?                                |                     | supports this?                                */
    /*                                               |                     |                                               */
    /* Filename                  have.sas7bdat       |                     | Filename                 have.sas7bdat        */
    /* Release Created           9.0401M7            |                     | Release Created          9.0401M7             */
    /* Host Created              X64_10PRO           |                     | Host Created             X64_10PRO            */
    /* File Size                 128KB               |                     | File Size                128KB                */
    /* File Size (bytes)         131072              |                     | File Size (bytes)        131072               */
    /*                                               |                     |                                               */
    /*   Variables in Creation Order                 |                     |  Variables in Creation Order                  */
    /*                                               |                     |                                               */
    /*  #    Variable    Type    Len                 |                     | #    Variable    Type    Len                  */
    /*                                               |                     |                                               */
    /*  1    Name        Char      8                 |                     | 1    Name        Char      8                  */
    /*  2    Sex         Char      1                 |                     | 2    Sex         Char      1                  */
    /*  3    Age         Num       8                 |                     | 3    Age         Num       8                  */
    /*  4    Height      Num       8                 |                     | 4    Height      Num       8                  */
    /*  5    Weight      Num       8                 |                     | 5    Weight      Num       8                  */
    /***********************************************************************************************************************/

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
