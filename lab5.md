### Lab Report 5 - Putting it All Together (Week 9)

Part 1 - Debugging Scenario


```
import java.io.File;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

public class prototype {

	static List<File> getFiles(File start) throws IOException {
	  File f = start;
	  List<File> result = new ArrayList<>();
	  result.add(start);
	  if(f.isDirectory()) {
	    File[] paths = f.listFiles();
	    for(File subFile: paths) {
	      result.add(subFile, 0);
	    }
	  }
	  return result;
	}
}
```

```
lab5/
|-  prototype.java
|-  tester.sh
```


Part 2 - Reflection

Coming into this course, I felt as if I had a relatively solid general understanding of how programming worked. Not super knowledgleable regarding specifics of any languages, but my overarching understanding of concepts felt pretty good. Upon taking this course, however, I realized how little I truly understood; Regarding Java, for example, a large majority of the topics taught in 15L have been either mostly or even completely foreign to me.
One concept that I have really found interesting, specifically, has been the utilization of the combination of the terminal and command prompts and lines. This was one of the few concepts that I had come across in some capacity prior to taking the class, but again, my previously engagement was extremely shallow compared to how deep the concepts actually go. A specific aspect of the command line prompts that have been intruiging for me, as well, is the usage of suffixes along with certain command lines to create sub-commands that specifically target special cases of the more general command. As I mentioned, it is a concept that I have come across before, even outside of programming, but seeing how powerful it actually is has been fascinating for me.
