# namesfromusingstreamsandfiles
package names.from.a.file.using.streams.and.files;
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.List;
import java.util.stream.Collectors;
/**
 *
 * @author 1BSCCSA51
 */
public class NamesFromAFileUsingStreamsAndFiles {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
     String inputFilePath = "input_names.txt";
String outputFilePath = "output_uppercase.txt";
try {  
   List<String> names = readNamesFromFile(inputFilePath); 
   List<String> uppercaseNames = names.stream()
.map(String::toUpperCase)
.collect(Collectors.toList());
 
   writeUppercaseNamesToFile(outputFilePath, uppercaseNames);
System.out.println("Uppercase names written to "+ outputFilePath);
} catch (IOException e) {

e.printStackTrace();
private static List<String> readNamesFromFile(String filePath) throws IOException {
try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {
return reader.lines().collect(Collectors.toList());
}
}
private static void writeUppercaseNamesToFile(String filePath, List<String>
uppercaseNames) throws IOException {
try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath))) {
for (String name : uppercaseNames) {
writer.write(name);
writer.newLine();
}
}
}
}

OUTPUT
ALICE
BOB
CHARLIE
DAVID
EVE
