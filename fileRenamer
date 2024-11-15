import java.io.File;
import java.text.DecimalFormat;
import java.util.Scanner;

public class FileRenamer {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user for the directory path
        System.out.print("Enter the directory path: ");
        String directoryPath = scanner.nextLine();

        // Prompt the user for the new base name
        System.out.print("Enter the new base name for the files: ");
        String baseName = scanner.nextLine();

        File folder = new File(directoryPath);
        File[] files = folder.listFiles();

        if (files == null || files.length == 0) {
            System.out.println("No files found in the specified folder.");
            return;
        }

        DecimalFormat format = new DecimalFormat("000");
        int counter = 1;

        for (File file : files) {
            if (file.isFile()) {
                String fileExtension = "";
                int extensionIndex = file.getName().lastIndexOf('.');
                if (extensionIndex > 0) {
                    fileExtension = file.getName().substring(extensionIndex);
                }

                String newFileName = baseName + "_" + format.format(counter) + fileExtension;
                File newFile = new File(folder, newFileName);

                if (file.renameTo(newFile)) {
                    System.out.println("Renamed: " + file.getName() + " -> " + newFileName);
                } else {
                    System.out.println("Failed to rename: " + file.getName());
                }

                counter++;
            }
        }

        scanner.close();
    }
}
