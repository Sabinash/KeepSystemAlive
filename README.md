# KeepSystemAlive
import java.awt.*;
import java.util.Calendar;
import java.util.Random;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class Sample {

    public static void main(String[] args) throws Exception {
        System.out.println("WelCome");
        System.out.println("KeepAlive is keeping your system awake for You");
        LocalDateTime myDateObj = LocalDateTime.now();
        DateTimeFormatter myFormatObj = DateTimeFormatter.ofPattern("dd-MM-yyyy");
        String formattedDate = myDateObj.format(myFormatObj);
        System.out.println("Today: " + formattedDate);
        Robot hal = new Robot();
        Random random = new Random();
        Calendar rightNow;
        int hour, minute, second;
        String time = "";
        while(true){
            rightNow = Calendar.getInstance( );
            hour = rightNow.get( Calendar.HOUR );
            minute = rightNow.get( Calendar.MINUTE );
            second = rightNow.get( Calendar.SECOND );
            time = ( hour >= 10 ? hour : "0" + hour ) + ":";
            time += ( minute >= 10 ? minute : "0" + minute ) + ":";
            time += ( second >= 10 ? second : "0" + second );
            Thread.sleep( 1000 );
        }

    }
}
