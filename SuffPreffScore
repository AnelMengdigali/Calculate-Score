import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.function.*;
import java.util.regex.*;
import java.util.stream.*;
import static java.util.stream.Collectors.joining;
import static java.util.stream.Collectors.toList;



class Result{
    
    public static String calculateScore( String text, String prefixString, String suffixString ) {
        
        String result = "";
        
        int score = 0;
        int score1 = 0;
        int score2 = 0;
        
        for ( int i = 0; i < text.length(); i ++ ) {
            
            for ( int j = i; j < text.length(); j ++ ) {
                
                String substring = text.substring( i, j + 1 );
                
                for ( int k = substring.length(); k >= 0; k -- ) {
                    
                    String prefix = substring.substring( 0, k );
                    
                    if ( prefixString.endsWith( prefix ) ) {
                        score1 = Math.max( prefix.length(), score1 );
                    }
                    
                }
                
                for ( int k = 0; k < substring.length(); k ++ ) {
                    
                    String suffix = substring.substring(k);
                    
                    if ( suffixString.startsWith( suffix ) ) {
                        score2 = Math.max( suffix.length(), score2 );
                    }
                    
                }
                
                if( score1 + score2 > score ){
                    
                    result = substring;
                    score = score1 + score2;
                    
                }
                
                if( score1 + score2 == score && substring.compareTo( result ) < 0 ){
                    result = substring;
                }
                
                score1 = 0;
                score2 = 0;
                
            }
            
        }
        
        return result;
        
    }
    
}
