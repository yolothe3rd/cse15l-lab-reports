### Lab Report 3 - Bugs and Commands (Week 5)

#### Part 1 - Bugs

1. Faulty input -
   ```
    @Test 
    public void testFilter() {
        int[] input = { "1", "3", "5" };
        assertArrayEquals(ListExamples.filter(input1, sc), ["1", "3", "5"]);
    }
   ```
   
2. NonFaulty Input -
   ```
    @Test 
    public void testFilter() {
        int[] input = { "1" };
        assertArrayEquals(ListExamples.filter(input1, sc), ["1"]);
    }
   ```
   
3. Symptoms
   Test 1 will be faulty, outputting `false`, as the output arraylist will be `["5", "3", "1"]` rather than the expected `["1", "3", "5"]`.
   Test 2 will not be faulty, outputting `true`, as the output arraylist will just simply be `["1"]`, which also the expected.
   
4. Before-After
   Before -
   ```
     static List<String> filter(List<String> list, StringChecker sc) {
      List<String> result = new ArrayList<>();
      for(String s: list) {
        if(sc.checkString(s)) {
          result.add(0, s);
        }
      }
      return result;
     }
   ```
   After -
   ```
     static List<String> filter(List<String> list, StringChecker sc) {
      List<String> result = new ArrayList<>();
      for(String s: list) {
        if(sc.checkString(s)) {
          result.add(s);
        }
      }
      return result;
     }
   ```

#### Part 2 - Researching Commands

The `find` command

  The `-name` option
  
  Example 1:
  
    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical/911report (main)
    $ find . -name "*.txt"
    ./chapter-1.txt
    ./chapter-10.txt
    ./chapter-11.txt
    ./chapter-12.txt
    ./chapter-13.1.txt
    ./chapter-13.2.txt
    ./chapter-13.3.txt
    ./chapter-13.4.txt
    ./chapter-13.5.txt
    ./chapter-2.txt
    ./chapter-3.txt
    ./chapter-5.txt
    ./chapter-6.txt
    ./chapter-7.txt
    ./chapter-8.txt
    ./chapter-9.txt
    ./preface.txt
    
  This example goes through the current working directory, `/c/Users/yolot/docsearch/technical/911report`, and searches for any file containing the `.txt` extension. This specific example shows how useful the `find` command can be for locating files of specific file types.

  Example 2:
  
    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical (main)
    $ find . -name "commission_report.txt"
    ./government/About_LSC/commission_report.txt

  This example goes through the current directory (`/c/Users/yolot/docsearch/technical`) and its subsequent subdirectories, and looks for a file named `cocmission_report.txt`, and returns its absolute path. This is useful for determining the absolute path of any specified file, as well as telling if it even exists in the first place. 
    
  The `-type d` option

  Example 1:

    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical (main)
    $ find . -type d
    .
    ./911report
    ./biomed
    ./government
    ./government/About_LSC
    ./government/Alcohol_Problems
    ./government/Env_Prot_Agen
    ./government/Gen_Account_Office
    ./government/Media
    ./government/Post_Rate_Comm
    ./plos

  This example (using the "`d`" specification) goes through the current directory (`/c/Users/yolot/docsearch/technical`) and finds, then prints, all the subdirectories. Useful for, of course, listing out all the subdirectories of the current working directory.

  Example 2:

    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical/government (main)
    $ find -type d
    .
    ./About_LSC
    ./Alcohol_Problems
    ./Env_Prot_Agen
    ./Gen_Account_Office
    ./Media
    ./Post_Rate_Comm

  This example, again using the `d` specification, goes through the current working directory (`/c/Users/yolot/docsearch/technical/government`), which is a subdirectory of `/technical`, and finds all the subdirectories of that subdirectory.

  The `-type f` option
  
  Example 1:

    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical/911report (main)
    $ find . -type f
    ./chapter-1.txt
    ./chapter-10.txt
    ./chapter-11.txt
    ./chapter-12.txt
    ./chapter-13.1.txt
    ./chapter-13.2.txt
    ./chapter-13.3.txt
    ./chapter-13.4.txt
    ./chapter-13.5.txt
    ./chapter-2.txt
    ./chapter-3.txt
    ./chapter-5.txt
    ./chapter-6.txt
    ./chapter-7.txt
    ./chapter-8.txt
    ./chapter-9.txt
    ./preface.txt

  This example goes through the current working directory (`/c/Users/yolot/docsearch/technical/911report`) and prints out the files (due to the `f` specification) within said directory. Nice for listing file contents of any given directory.

  Example 2:
    
    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical/plos (main)
    $ find . -type f -name "journal.*.*.txt"
    ./journal.pbio.0020001.txt
    ./journal.pbio.0020010.txt
    ./journal.pbio.0020012.txt
    ./journal.pbio.0020013.txt
    ./journal.pbio.0020019.txt
    ./journal.pbio.0020028.txt
    ./journal.pbio.0020035.txt
    ./journal.pbio.0020040.txt
    ./journal.pbio.0020042.txt
    ./journal.pbio.0020043.txt
    ./journal.pbio.0020046.txt
    ./journal.pbio.0020047.txt
    ./journal.pbio.0020052.txt
    ./journal.pbio.0020053.txt
    ./journal.pbio.0020054.txt
    ./journal.pbio.0020063.txt
    ./journal.pbio.0020064.txt
    ./journal.pbio.0020067.txt
    ./journal.pbio.0020068.txt
    ./journal.pbio.0020071.txt
    ./journal.pbio.0020073.txt
    ./journal.pbio.0020100.txt
    ./journal.pbio.0020101.txt
    ./journal.pbio.0020105.txt
    ./journal.pbio.0020112.txt
    ./journal.pbio.0020113.txt
    ./journal.pbio.0020116.txt
    ./journal.pbio.0020121.txt
    ./journal.pbio.0020125.txt
    ./journal.pbio.0020127.txt
    ./journal.pbio.0020133.txt
    ./journal.pbio.0020140.txt
    ./journal.pbio.0020145.txt
    ./journal.pbio.0020146.txt
    ./journal.pbio.0020147.txt
    ./journal.pbio.0020148.txt
    ./journal.pbio.0020150.txt
    ./journal.pbio.0020156.txt
    ./journal.pbio.0020161.txt
    ./journal.pbio.0020164.txt
    ./journal.pbio.0020169.txt
    ./journal.pbio.0020172.txt
    ./journal.pbio.0020183.txt
    ./journal.pbio.0020187.txt
    ./journal.pbio.0020190.txt
    ./journal.pbio.0020206.txt
    ./journal.pbio.0020213.txt
    ./journal.pbio.0020214.txt
    ./journal.pbio.0020215.txt
    ./journal.pbio.0020216.txt
    ./journal.pbio.0020223.txt
    ./journal.pbio.0020224.txt
    ./journal.pbio.0020228.txt
    ./journal.pbio.0020232.txt
    ./journal.pbio.0020241.txt
    ./journal.pbio.0020262.txt
    ./journal.pbio.0020263.txt
    ./journal.pbio.0020267.txt
    ./journal.pbio.0020272.txt
    ./journal.pbio.0020276.txt
    ./journal.pbio.0020297.txt
    ./journal.pbio.0020302.txt
    ./journal.pbio.0020306.txt
    ./journal.pbio.0020307.txt
    ./journal.pbio.0020310.txt
    ./journal.pbio.0020311.txt
    ./journal.pbio.0020337.txt
    ./journal.pbio.0020346.txt
    ./journal.pbio.0020347.txt
    ./journal.pbio.0020348.txt
    ./journal.pbio.0020350.txt
    ./journal.pbio.0020353.txt
    ./journal.pbio.0020354.txt
    ./journal.pbio.0020394.txt
    ./journal.pbio.0020400.txt
    ./journal.pbio.0020401.txt
    ./journal.pbio.0020404.txt
    ./journal.pbio.0020406.txt
    ./journal.pbio.0020419.txt
    ./journal.pbio.0020420.txt
    ./journal.pbio.0020430.txt
    ./journal.pbio.0020431.txt
    ./journal.pbio.0020439.txt
    ./journal.pbio.0020440.txt
    ./journal.pbio.0030021.txt
    ./journal.pbio.0030024.txt
    ./journal.pbio.0030032.txt
    ./journal.pbio.0030050.txt
    ./journal.pbio.0030051.txt
    ./journal.pbio.0030056.txt
    ./journal.pbio.0030062.txt
    ./journal.pbio.0030065.txt
    ./journal.pbio.0030076.txt
    ./journal.pbio.0030094.txt
    ./journal.pbio.0030097.txt
    ./journal.pbio.0030102.txt
    ./journal.pbio.0030105.txt
    ./journal.pbio.0030127.txt
    ./journal.pbio.0030129.txt
    ./journal.pbio.0030131.txt
    ./journal.pbio.0030136.txt
    ./journal.pbio.0030137.txt

  This example combines the `find -f` command specification with the `-name` option, and finds all normal files with names in the format `journal.*.*.txt` in the current working directory.

  The `-atime` option

  Example 1: 

    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical/government/About_LSC (main)
    $ find . -atime +14

  This example goes through the current working directory and lists the files that have been opened/accessd more than 14 days ago (specified by the `+14`, meaning more than 14 days). Nothing is returned or printed, as none of the files within this subdirectory have been accessed more than 14 days ago.
  
  Example 2:

    yolot@TABLET-81HN2PAV MINGW64 ~/docsearch/technical/government/About_LSC (main)
    $ find . -atime -1
    .
    ./Comments_on_semiannual.txt
    ./commission_report.txt
    ./conference_highlights.txt
    ./CONFIG_STANDARDS.txt
    ./diversity_priorities.txt
    ./LegalServCorp_v_VelazquezDissent.txt
    ./LegalServCorp_v_VelazquezOpinion.txt
    ./LegalServCorp_v_VelazquezSyllabus.txt
    ./ODonnell_et_al_v_LSCdecision.txt
    ./ONTARIO_LEGAL_AID_SERIES.txt
    ./Progress_report.txt
    ./Protocol_Regarding_Access.txt
    ./reporting_system.txt
    ./Special_report_to_congress.txt
    ./State_Planning_Report.txt
    ./State_Planning_Special_Report.txt
    ./Strategic_report.txt

  This example goes through the current working directory and lists the files that have been opened/accessed within the last day (specified by the `-1`, meaning less than 1 day). Useful for going back and checking the list of files that have been accessed for any purpose.
