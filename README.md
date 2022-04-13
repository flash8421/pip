Creative Commons Legal Code

CC0 1.0 Universal

    CREATIVE COMMONS CORPORATION IS NOT A LAW FIRM AND DOES NOT PROVIDE
    LEGAL SERVICES. DISTRIBUTION OF THIS DOCUMENT DOES NOT CREATE AN
    ATTORNEY-CLIENT RELATIONSHIP. CREATIVE COMMONS PROVIDES THIS
    INFORMATION ON AN "AS-IS" BASIS. CREATIVE COMMONS MAKES NO WARRANTIES
    REGARDING THE USE OF THIS DOCUMENT OR THE INFORMATION OR WORKS
    PROVIDED HEREUNDER, AND DISCLAIMS LIABILITY FOR DAMAGES RESULTING FROM
    THE USE OF THIS DOCUMENT OR THE INFORMATION OR WORKS PROVIDED
    HEREUNDER.

Statement of Purpose

The laws of most jurisdictions throughout the world automatically confer
exclusive Copyright and Related Rights (defined below) upon the creator
and subsequent owner(s) (each and all, an "owner") of an original work of
authorship and/or a database (each, a "Work").

Certain owners wish to permanently relinquish those rights to a Work for
the purpose of contributing to a commons of creative, cultural and
scientific works ("Commons") that the public can reliably and without fear
of later claims of infringement build upon, modify, incorporate in other
works, reuse and redistribute as freely as possible in any form whatsoever
and for any purposes, including without limitation commercial purposes.
These owners may contribute to the Commons to promote the ideal of a free
culture and the further production of creative, cultural and scientific
works, or to gain reputation or greater distribution for their Work in
part through the use and efforts of others.

For these and/or other purposes and motivations, and without any
expectation of additional consideration or compensation, the person
associating CC0 with a Work (the "Affirmer"), to the extent that he or she
is an owner of Copyright and Related Rights in the Work, voluntarily
elects to apply CC0 to the Work and publicly distribute the Work under its
terms, with knowledge of his or her Copyright and Related Rights in the
Work and the meaning and intended legal effect of CC0 on those rights.

1. Copyright and Related Rights. A Work made available under CC0 may be
protected by copyright and related or neighboring rights ("Copyright and
Related Rights"). Copyright and Related Rights include, but are not
limited to, the following:

  i. the right to reproduce, adapt, distribute, perform, display,
     communicate, and translate a Work;
 ii. moral rights retained by the original author(s) and/or performer(s);
iii. publicity and privacy rights pertaining to a person's image or
     likeness depicted in a Work;
 iv. rights protecting against unfair competition in regards to a Work,
     subject to the limitations in paragraph 4(a), below;
  v. rights protecting the extraction, dissemination, use and reuse of data
     in a Work;
 vi. database rights (such as those arising under Directive 96/9/EC of the
     European Parliament and of the Council of 11 March 1996 on the legal
     protection of databases, and under any national implementation
     thereof, including any amended or successor version of such
     directive); and
vii. other similar, equivalent or corresponding rights throughout the
     world based on applicable law or treaty, and any national
     implementations thereof.

2. Waiver. To the greatest extent permitted by, but not in contravention
of, applicable law, Affirmer hereby overtly, fully, permanently,
irrevocably and unconditionally waives, abandons, and surrenders all of
Affirmer's Copyright and Related Rights and associated claims and causes
of action, whether now known or unknown (including existing as well as
future claims and causes of action), in the Work (i) in all territories
worldwide, (ii) for the maximum duration provided by applicable law or
treaty (including future time extensions), (iii) in any current or future
medium and for any number of copies, and (iv) for any purpose whatsoever,
including without limitation commercial, advertising or promotional
purposes (the "Waiver"). Affirmer makes the Waiver for the benefit of each
member of the public at large and to the detriment of Affirmer's heirs and
successors, fully intending that such Waiver shall not be subject to
revocation, rescission, cancellation, termination, or any other legal or
equitable action to disrupt the quiet enjoyment of the Work by the public
as contemplated by Affirmer's express Statement of Purpose.

3. Public License Fallback. Should any part of the Waiver for any reason
be judged legally invalid or ineffective under applicable law, then the
Waiver shall be preserved to the maximum extent permitted taking into
account Affirmer's express Statement of Purpose. In addition, to the
extent the Waiver is so judged Affirmer hereby grants to each affected
person a royalty-free, non transferable, non sublicensable, non exclusive,
irrevocable and unconditional license to exercise Affirmer's Copyright and
Related Rights in the Work (i) in all territories worldwide, (ii) for the
maximum duration provided by applicable law or treaty (including future
time extensions), (iii) in any current or future medium and for any number
of copies, and (iv) for any purpose whatsoever, including without
limitation commercial, advertising or promotional purposes (the
"License"). The License shall be deemed effective as of the date CC0 was
applied by Affirmer to the Work. Should any part of the License for any
reason be judged legally invalid or ineffective under applicable law, such
partial invalidity or ineffectiveness shall not invalidate the remainder
of the License, and in such case Affirmer hereby affirms that he or she
will not (i) exercise any of his or her remaining Copyright and Related
Rights in the Work or (ii) assert any associated claims and causes of
action with respect to the Work, in either case contrary to Affirmer's
express Statement of Purpose.


public class bitwise{
public static void main(String args[]){
int a=60,b=30;
int c;
c=a & b;
System.out.println("Bitwise and operation="+c);
c=a | b;
System.out.println("Bitwise or operation="+c);
c=a ^ b;
System.out.println("Bitwise xor operation="+c);
c=~a;
System.out.println("Bitwise not operation="+c);
c=a<<2;
System.out.println("Bitwise left shift operation="+c);
c=a>>2;
System.out.println("Bitwise right shift operation="+c);
c=a>>>2;
System.out.println("Bitwise unsigned right operation="+c);
}
}






import java.util.*;
import java.io.*;
public class PageRank {

 public int path[][] = new int[10][10];
 public double pagerank[] = new double[10];

 public void calc(double totalNodes) {

  double InitialPageRank;
  double OutgoingLinks = 0;
  double DampingFactor = 0.85;
  double TempPageRank[] = new double[10];
  int ExternalNodeNumber;
  int InternalNodeNumber;
  int k = 1; // For Traversing
  int ITERATION_STEP = 1;
  InitialPageRank = 1 / totalNodes;
  System.out.printf(" Total Number of Nodes :" + totalNodes + "\t Initial PageRank  of All Nodes :" + InitialPageRank + "\n");

  // 0th ITERATION  _ OR _ INITIALIZATION PHASE //
  
  for (k = 1; k <= totalNodes; k++) {
   this.pagerank[k] = InitialPageRank;
  }

  System.out.printf("\n Initial PageRank Values , 0th Step \n");
  for (k = 1; k <= totalNodes; k++) {
   System.out.printf(" Page Rank of " + k + " is :\t" + this.pagerank[k] + "\n");
  }

  while (ITERATION_STEP <= 2) // Iterations
  {
   // Store the PageRank for All Nodes in Temporary Array 
   for (k = 1; k <= totalNodes; k++) {
    TempPageRank[k] = this.pagerank[k];
    this.pagerank[k] = 0;
   }

   for (InternalNodeNumber = 1; InternalNodeNumber <= totalNodes; InternalNodeNumber++) {
    for (ExternalNodeNumber = 1; ExternalNodeNumber <= totalNodes; ExternalNodeNumber++) {
     if (this.path[ExternalNodeNumber][InternalNodeNumber] == 1) {
      k = 1;
      OutgoingLinks = 0; // Count the Number of Outgoing Links for each ExternalNodeNumber
      while (k <= totalNodes) {
       if (this.path[ExternalNodeNumber][k] == 1) {
        OutgoingLinks = OutgoingLinks + 1; // Counter for Outgoing Links
       }
       k = k + 1;
      }
      // Calculate PageRank     
      this.pagerank[InternalNodeNumber] += TempPageRank[ExternalNodeNumber] * (1 / OutgoingLinks);
     }
    }
   }

   System.out.printf("\n After " + ITERATION_STEP + "th Step \n");

   for (k = 1; k <= totalNodes; k++)
    System.out.printf(" Page Rank of " + k + " is :\t" + this.pagerank[k] + "\n");

   ITERATION_STEP = ITERATION_STEP + 1;
  }
  // Add the Damping Factor to PageRank
  for (k = 1; k <= totalNodes; k++) {
   this.pagerank[k] = (1 - DampingFactor) + DampingFactor * this.pagerank[k];
  }

  // Display PageRank
  System.out.printf("\n Final Page Rank : \n");
  for (k = 1; k <= totalNodes; k++) {
   System.out.printf(" Page Rank of " + k + " is :\t" + this.pagerank[k] + "\n");
  }

 }
 
 public static void main(String args[]) {
  int nodes, i, j, cost;
  Scanner in = new Scanner(System.in);
  System.out.println("Enter the Number of WebPages \n");
  nodes = in .nextInt();
  PageRank p = new PageRank();
  System.out.println("Enter the Adjacency Matrix with 1->PATH & 0->NO PATH Between two WebPages: \n");
  for (i = 1; i <= nodes; i++)
   for (j = 1; j <= nodes; j++) {
    p.path[i][j] = in .nextInt();
    if (j == i)
     p.path[i][j] = 0;
   }
  p.calc(nodes);

 }
}







public class EditDistanceProblem {
 public int editDistanceDP(String s1, String s2) {
 int [][] solution = new int[s1.length()+1][s2.length()+1];  
 //base case
 //If any of the string if empty then number of operations  //needed would be equal to the length of other string  //(Either all characters will be removed or inserted)
 
 for (int i = 0; i <=s2.length(); i++) { 
solution[0][i] =i;
 }
 for (int i = 0; i <=s1.length(); i++) {
 solution[i][0] =i;
 }
 //solving it bottom-up manner
 int m = s1.length();
 int n = s2.length();
 for (int i = 1; i <=m ; i++) {
 for (int j = 1; j <=n ; j++) {
 //If last characters are matching, ignore the last character
 // then the solution will be same as without the last  character.
 if(s1.charAt(i-1)==s2.charAt(j-1))
 solution[i][j] = solution[i-1][j-1];
 else
 solution[i][j] = 1 + Math.min(solution[i][j-1],
 Math.min(solution[i-1][j],
 solution[i-1][j-1]));
 }
 }
 
 
 return solution[s1.length()][s2.length()];
 }
 public static void main(String[] args) {
 String s1 = "horizon";
 String s2 = "horizontal";
 EditDistanceProblem ed = new EditDistanceProblem();
 System.out.println("Minimum Edit Distance -(DP): " +  ed.editDistanceDP(s1, s2));
 }
}
public static void main(String[] args) { 
 String s1 = "horizon"; 
 String s2 = "horizontal"; 
 EditDistanceProblem ed = new EditDistanceProblem(); 
 System.out.println("Minimum Edit Distance -(Recursion): " +  ed.editDistanceRecursion(s1, s2, s1.length(), s2.length())); 
 } 
}





import java.io.BufferedReader; 
import java.io.FileReader; 
import java.io.IOException; 
public class CompareTextFiles 
{  
 public static void main(String[] args) throws IOException  {  
 BufferedReader reader1 = new BufferedReader(new  FileReader("file1.txt")); 
  
 BufferedReader reader2 = new BufferedReader(new  FileReader("file2.txt")); 
  
 String line1 = reader1.readLine(); 
  
 String line2 = reader2.readLine(); 
  
 boolean areEqual = true; 
  
 int lineNum = 1;
  
 while (line1 != null || line2 != null)  { 
 if(line1 == null || line2 == null)  { 
 areEqual = false; 
  
 break; 
 } 
 else if(! line1.equalsIgnoreCase(line2))  { 
 areEqual = false; 
  
 break; 
 } 
  
 line1 = reader1.readLine(); 
  
 line2 = reader2.readLine(); 
  
 lineNum++; 
 } 
  
 if(areEqual) 
 {
 System.out.println("Two files have same content.");  } 
 else 
 { 
 System.out.println("Two files have different content. They  differ at line "+lineNum); 
  
 System.out.println("File1 has "+line1+" and File2 has  "+line2+" at line "+lineNum); 
 } 
  
 reader1.close(); 
  
 reader2.close(); 
 } 
}






from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

example_sent="Hello how are you."
stop_words = set(stopwords.words('english'))

word_tokens = word_tokenize(example_sent)

filtered_sentence = [w for w in word_tokens if not w in stop_words]

filtered_sentence = []

for w in word_tokens:
    if w not in stop_words:
        filtered_sentence.append(w)
print("given sentence :",word_tokens)
print("stop word removal:",filtered_sentence)





import requests
from bs4 import BeautifulSoup

url=("www.amazon.in")
code=requests.get("https://" +url)
plain=code.text
s=BeautifulSoup(plain)
for link in s.find_all("a"):
    print(link.get("href"))




import csv
import requests
import xml.etree.ElementTree as ET
	
        
def parseXML(xmlfile):
    # create element tree object
    tree = ET.parse(xmlfile)
    # get root element
    root = tree.getroot()
    # create empty list for news items
    newsitems = []
    # iterate news items
    for item in root.findall('./channel/item'):
        # empty news dictionary
        news = {}
        # iterate child elements of item
        for child in item:
            # special checking for namespace object content:media
            if child.tag == '{http://search.yahoo.com/mrss/}content':
                news['media'] = child.attrib['url']
            else:
                news[child.tag] = child.text.encode('utf8')
        # append news dictionary to news items list
        newsitems.append(news)
    
    # return news items list
    return newsitems
def savetoCSV(newsitems, filename):
    # specifying the fields for csv file
    field_names = ['guid', 'title', 'pubDate', 'description', 'link', 'media']
    # writing to csv file
    with open(filename, 'w') as csvfile:
        # creating a csv dict writer object
        writer = csv.DictWriter(csvfile, fieldnames = field_names,extrasaction='ignore')
        # writing headers (field names)
        writer.writeheader()
        # writing data rows
        writer.writerows(newsitems)

    
def main():
    # load rss from web to update existing xml file
    # parse xml file
    newsitems = parseXML('rssfeed.xml')
    print (newsitems)
    # store news items in a csv file
    savetoCSV(newsitems, 'topnews.csv')
    
    
if __name__ == "__main__":
    # calling main function
    main()


Limitations and Disclaimers.

 a. No trademark or patent rights held by Affirmer are waived, abandoned,
    surrendered, licensed or otherwise affected by this document.
 b. Affirmer offers the Work as-is and makes no representations or
    warranties of any kind concerning the Work, express, implied,
    statutory or otherwise, including without limitation warranties of
    title, merchantability, fitness for a particular purpose, non
    infringement, or the absence of latent or other defects, accuracy, or
    the present or absence of errors, whether or not discoverable, all to
    the greatest extent permissible under applicable law.
 c. Affirmer disclaims responsibility for clearing rights of other persons
    that may apply to the Work or any use thereof, including without
    limitation any person's Copyright and Related Rights in the Work.
    Further, Affirmer disclaims responsibility for obtaining any necessary
    consents, permissions or other rights required for any use of the
    Work.
 d. Affirmer understands and acknowledges that Creative Commons is not a
    party to this document and has no duty or obligation with respect to
    this CC0 or use of the Work.
