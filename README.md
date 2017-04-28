# readfile
Test: this is in java version application that provides the following APIs: - API to upload a file with a few meta-data fields. - API to get file meta-data - (Optional) API to download content stream - (Optional) API to search for file IDs with a search criterion 
package test;
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.util.Arrays;
/**
 * Test: this is in java version
Imlement a RESTFul API spring-boot application that provides the following APIs:
- API to upload a file with a few meta-data fields. Persist meta-data in persistence store (In memory DB or file system and store the content on a file system)
- API to get file meta-data
- (Optional) API to download content stream
- (Optional) API to search for file IDs with a search criterion 
- (Optional) Write a scheduler in the same app to poll for new items in the last hour and send an email
 * @author Rocio
 *
 */
public class UploadFile {

	public static void main(String[] args) throws IOException {
		// path where the file is located
		String file = "C:/Users/Rocio/Desktop/test.txt";
		String thisLine = null;
	    int rows = 9;
		String [][] studentScore = new String[rows][];
		//using try and catch to catch mistakes
		try{
		// open input stream test.txt for reading purpose.
         BufferedReader br = new BufferedReader(new FileReader(file));
         int len = 0;
         
         while ((thisLine = br.readLine()) != null) {
             studentScore[len++] = thisLine.split(",");
          
         } 
         //counting the number of males
         int count = 0;
         String comp = "male";
			for (int i = 0; i < studentScore.length; i++){
				if (comp.equals(studentScore[i][1])){
	            ++count;
	            
	            }
	          }
			//printing results
			System.out.println(Arrays.deepToString(studentScore));//print all the 2d array
			System.out.println("the number of occurrence of male is: " + count);//print the number of males
			br.close();
		}
			catch (FileNotFoundException ex){
			System.out.println("file not found");
		}
	}
}
