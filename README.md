# CBT702
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 702 is from Stephen McColley and contains JES2 usermods   *   FILE 702
//*           at both the z/OS 1.6 and z/OS 1.4 levels, These       *   FILE 702
//*           usermods may be considered replacements for the old   *   FILE 702
//*           Mellon Bank mods to JES2.                             *   FILE 702
//*                                                                 *   FILE 702
//*           The principal maintainer of the Mellon Mods           *   FILE 702
//*           is Stephen McColley.                                  *   FILE 702
//*                                                                 *   FILE 702
//*           McColley Systems Group Inc.                           *   FILE 702
//*           sgmccolley@windstream.net                             *   FILE 702
//*           SGMcColley@MVSProgrammer.com                          *   FILE 702
//*           http://WWW.MVSProgrammer.com                          *   FILE 702
//*           770-335-0478                                          *   FILE 702
//*                                                                 *   FILE 702
//*   For compatibility issues, please see the member $$NOTE0       *   FILE 702
//*   which was written by Stephen McColley.                        *   FILE 702
//*                                                                 *   FILE 702
//*   Please see member $$$$PKG describing the packaging of this    *   FILE 702
//*   pds first, before attempting to install either the z/OS 1.6   *   FILE 702
//*   or z/OS 1.4 versions of the SunTrust JES2 mods.               *   FILE 702
//*                                                                 *   FILE 702
//*   The z/OS 1.6 installation pds can be created by customizing   *   FILE 702
//*   and running job $PDSLO16 which is included in this pds.       *   FILE 702
//*                                                                 *   FILE 702
//*   The z/OS 1.4 installation pds can be created by customizing   *   FILE 702
//*   and running job $PDSLO14 which is included in this pds.       *   FILE 702
//*                                                                 *   FILE 702
//*   Description of the JES2 Usermods (from the z/OS 1.6 version)  *   FILE 702
//*                                                                 *   FILE 702
//*       ALL OF OUR USERMODS ARE IN MVS.OSMAINT.USERMODS ON        *   FILE 702
//*       THE TECPLEX.                                              *   FILE 702
//*                                                                 *   FILE 702
//*       Each usermod(LSES5**) member has a corresponding          *   FILE 702
//*       member suffixed with a "J".  The members with the "J"     *   FILE 702
//*       suffixes are sample jcl install members.                  *   FILE 702
//*                                                                 *   FILE 702
//*       FOR JES2 WE HAVE THE FOLLOWING usermods - These are       *   FILE 702
//*       ALL of our JES2 mods.  Most folks who are interested      *   FILE 702
//*       in only using the Mellon Mods should refer to the         *   FILE 702
//*       next section, entitled -                                  *   FILE 702
//*                                                                 *   FILE 702
//*       " THE FOLLOWING CAN BE CONSIDERED MELLON MOD              *   FILE 702
//*       REPLACEMENTS "                                            *   FILE 702
//*                                                                 *   FILE 702
//*     All of our JES2 usermods:                                   *   FILE 702
//*                                                                 *   FILE 702
//*   MOD NAME   IMPLEMENTED     LMOD NAME   DESCRIPTION            *   FILE 702
//*   LSES500   ZOS6-09/01/2005  STJTABS  - CREATES OUR EXTENSIONS  *   FILE 702
//*                                         TO JQE AND JCT          *   FILE 702
//*   LSES502   ZOS6-09/01/2005  STSCX01A - JES2 EXIT1 - BANNER     *   FILE 702
//*                                         PAGE EXIT (NON 3800)    *   FILE 702
//*   LSES503   ZOS6-09/01/2005  STSCX04A - parses /*ROUTE cards    *   FILE 702
//*   LSES504   ZOS6-09/01/2005  STSCX04B - PARSES                  *   FILE 702
//*                                         /*BEFORE/*AFTER/*WITH   *   FILE 702
//*                                         AND /*CNTL              *   FILE 702
//*   LSES505   ZOS6-09/01/2005  STSCX05A - PROCESS $REPEXIT AND    *   FILE 702
//*                                         $ADDEXIT COMMANDS       *   FILE 702
//*   LSES506   ZOS6-09/01/2005  STSCX05B - prevents purging jobs   *   FILE 702
//*                                         by range                *   FILE 702
//*   LSES507   ZOS6-09/01/2005  STSCX06A - MOVES VALID XEQ VALUES  *   FILE 702
//*                                         TO SCHENV VALUES        *   FILE 702
//*   LSES509   ZOS6-09/01/2005  STSCX15A - FORCES FCB LOAD UNLESS  *   FILE 702
//*                                         CHANGING STD FORMS      *   FILE 702
//*   LSES510   ZOS6-09/01/2005  STSCX20A - END OF INPUT - MOVE     *   FILE 702
//*                                         JCT INFO TO JQE         *   FILE 702
//*   LSES511   ZOS6-09/01/2005  STSCX36A - SAF process of RJE      *   FILE 702
//*                                         submitted jobs          *   FILE 702
//*   LSES512   ZOS6-09/01/2005  STSCX49A - IMPLEMENT               *   FILE 702
//*                                         BEFORE|AFTER|WITH|CNTL  *   FILE 702
//*                                         USAGE                   *   FILE 702
//*   LSES513   ZOS6-09/01/2005  STSCX100 - FCB SETUP /             *   FILE 702
//*                                         TRANSLATION USER        *   FILE 702
//*                                         EXIT100                 *   FILE 702
//*   LSES514   ZOS6-09/01/2005  HASPPRPU - INSERT USER EXIT100     *   FILE 702
//*                                         INTO HASPPRPU CODE      *   FILE 702
//*   -------- ---------------   -------------------------------    *   FILE 702
//*                                                                 *   FILE 702
//*      ***********                                                *   FILE 702
//*                                                                 *   FILE 702
//*     OF THESE MODS, THE FOLLOWING CAN BE                         *   FILE 702
//*     CONSIDERED MELLON MOD REPLACEMENTS                          *   FILE 702
//*                                                                 *   FILE 702
//*      ***********                                                *   FILE 702
//*                                                                 *   FILE 702
//*   MOD NAME   IMPLEMENTED     LMOD NAME   DESCRIPTION            *   FILE 702
//*   LSES500   ZOS6-09/01/2005  STJTABS  - CREATES OUR EXTENSIONS  *   FILE 702
//*                                         TO JQE AND JCT          *   FILE 702
//*   LSES503   zOS6-09/01/2005  STSCX04A - parses /*ROUTE cards    *   FILE 702
//*   LSES504   ZOS6-09/01/2005  STSCX04B - PARSES                  *   FILE 702
//*                                         /*BEFORE/*AFTER/*WITH   *   FILE 702
//*                                         AND /*CNTL              *   FILE 702
//*   LSES507   ZOS6-09/01/2005  STSCX06A - MOVES VALID XEQ VALUES  *   FILE 702
//*                                         TO SCHENV VALUES        *   FILE 702
//*   LSES510   ZOS6-09/01/2005  STSCX20A - END OF INPUT - MOVE     *   FILE 702
//*                                         JCT INFO TO JQE         *   FILE 702
//*   LSES512   ZOS6-09/01/2005  STSCX49A - IMPLEMENT               *   FILE 702
//*                                         BEFORE|AFTER|WITH|CNTL  *   FILE 702
//*                                         USAGE                   *   FILE 702
//*                                                                 *   FILE 702
//*      ***********                                                *   FILE 702
//*                                                                 *   FILE 702
//*      The installation instructions for the Mellon MODs          *   FILE 702
//*      only, can be found in member DOCINS.                       *   FILE 702
//*                                                                 *   FILE 702
//*      The overview documentation for the mellon mods is in       *   FILE 702
//*      member DOCOVW.                                             *   FILE 702
//*                                                                 *   FILE 702
//*      The user documentation for the mellon mods is in           *   FILE 702
//*      member DOCUSR.                                             *   FILE 702
//*                                                                 *   FILE 702
//*      ***********                                                *   FILE 702
//*                                                                 *   FILE 702
//*         * * * PLEASE NOTE ! * * *                               *   FILE 702
//*                                                                 *   FILE 702
//*        SPECIAL THANKS GO TO BOB BREAK OF ST. LOUIS FOR          *   FILE 702
//*      THE ORIGINAL CODE TO PARSE THE "/*ROUTE XEQ RESNAME"       *   FILE 702
//*      CARDS AND SET THE APPROPRIATE EXECUTION ENVIRONMENT.       *   FILE 702
//*                                                                 *   FILE 702
//*        SPECIAL THANKS TO JUDY RUNT OF WISCONSIN ELECTRIC        *   FILE 702
//*      FOR THE ORIGINAL CODE TO HANDLE THE "/*CNTL                *   FILE 702
//*      BEFORE|AFTER|WITH,RESNAME" AND "/*CNTL                     *   FILE 702
//*      RESNAME,EXC|SHR" ROUTINES.  THE USE OF THE BLOCK           *   FILE 702
//*      EXTENSION REUSABLE TABLES, and BERT'S, TO EXTEND THE       *   FILE 702
//*      JCT AND JQE.                                               *   FILE 702
//*                                                                 *   FILE 702
//*      Although some changes have been made to all of the         *   FILE 702
//*      code, their combined help was invaluable.                  *   FILE 702
//*                                                                 *   FILE 702
```
