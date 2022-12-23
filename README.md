###  [Task 6 kyu](https://www.codewars.com/kata/583203e6eb35d7980400002a/train/java)
Given an array (arr) as an argument complete the function countSmileys that should return the total number of smiling faces.

Rules for a smiling face:

    Each smiley face must contain a valid pair of eyes. Eyes can be marked as : or ;
    A smiley face can have a nose but it does not have to. Valid characters for a nose are - or ~
    Every smiling face must have a smiling mouth that should be marked with either ) or D

No additional characters are allowed except for those mentioned.

Valid smiley face examples: :) :D ;-D :~)
Invalid smiley faces: ;( :> :} :]
Example

countSmileys([':)', ';(', ';}', ':-D']);       // should return 2;
countSmileys([';D', ':-(', ':-)', ';~)']);     // should return 3;
countSmileys([';]', ':[', ';*', ':$', ';-D']); // should return 1;


### My solution
```Java
import java.util.*;

public class SmileFaces {
    public static int countSmileys(List<String> arr) {
        String validSmileRegExp = "[:;][-~]?[)D]";
        int smiles = 0;
        for (String smile : arr) {
            if (smile.matches(validSmileRegExp)) {
                smiles += 1;
            }
        }
        return smiles;
    }
}

```

### Fav solution
```Java
import java.util.*;

public class SmileFaces {

    public static int countSmileys(List<String> arr) {
        return (int) arr.stream()
                .filter(x -> x.matches("[:;][~-]?[)D]"))
                .count();
    }
}
```
I like this solution because I like it
