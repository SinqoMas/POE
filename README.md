# POE
tasks of the POE
import java.util.Scanner;
public class Kanban {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Scanner choice = new Scanner(System.in); 
        int taskNo=0, taskDur, num, totalHours[];
        String taskName, taskDescrip, dev,dev3="",taskID="", taskStat, quit;
        
        System.out.println("Welcome to EasyKanban");
        System.out.println("1. Add task");
        System.out.println("2. Show report(Coming Soon!)");
        System.out.println("3. Quit");
        System.out.println();
        System.out.println("Enter \"1\", \"2\" or \"3\"");
        int entry = choice.nextInt();
              
       switch(entry){
           case 1: 
               System.out.println("Add task");
               System.out.println("What is the name of the task?");
               taskName = choice.nextLine();
               System.out.println("What is the description of the task?");
               taskDescrip = choice.nextLine();             
               System.out.println("What is the developer's details?");
               dev = choice.nextLine();
               System.out.println("What is the duration of the task?");
               taskDur = choice.nextInt();
               System.out.println(createTaskID(taskID, dev, dev3, taskName, taskNo));
               System.out.println("What is the status of the task");
               System.out.println("1 - to do");
               System.out.println("2 - done");
               System.out.println("3 - doing");
               System.out.println("Enter \"1\", \"2\" or \"3\"");
               num = choice.nextInt();
               if (num == 1){
                   taskStat = "to do";
               }
               else if (num == 2){
                   taskStat = "done";
               }
               else if (num == 3){
                   taskStat = "doing";
               }
               taskNo = taskNo + 1;
            break;
            case 2: 
               System.out.println("Show report");
            break;
            case 3: 
               System.out.println("Goodbye");
               quit = choice.nextLine();
            break;
       }
    }
     public static boolean checkTaskDescription(String taskDescrip){
         if (taskDescrip.length() > 50){
                   System.out.println("This description should not exceed 50 charaters");               
                   return false;
               }
               else{
                   System.out.println("Task successfully captured");
               }
         return true;
     } 
     public static String createTaskID(String taskID, String dev, String dev3, String taskName, int taskNo){
         if (dev.length() > 3){
            dev3 = dev.substring(dev.length()-3);
        }
        else{
            dev3 = dev;
         }
        return taskID = taskName + ":" + taskNo + ":" + dev3; 
     }
}
