# 1. Repository
My repository
[link](https://github.com/DongyangLi6816/markdown-parse)

MarkdwonParse I reviewed
[Reviewed](https://github.com/IncogOwl/markdown-parse)

# 2. Test
Below is the Junit test I wrote according to VScode preview
```
    @Test
    public void testSnippet1() throws IOException {
        String contents= Files.readString(Path.of("snippet1.md"));
        List<String> expect = List.of("`google.com", "google.com", "ucsd.edu");
        assertEquals(expect, MarkdownParse.getLinks(contents));
    }

    @Test
    public void testSnippet2() throws IOException {
        String contents= Files.readString(Path.of("./snippet2.md"));
        List<String> expect = List.of("a.com","a.com(())", "exmaple.com");
        assertEquals(expect, MarkdownParse.getLinks(contents));
    }

    @Test
    public void testSnippet3() throws IOException {
        String contents= Files.readString(Path.of("snippet3.md"));
        List<String> expect = List.of("https://ucsd-cse15l-w22.github.io/");
        assertEquals(expect, MarkdownParse.getLinks(contents));
    }
```

![image](https://user-images.githubusercontent.com/97556577/155816769-0f7fb957-fc47-4584-a216-f92236e49c63.png)

# 3. Result
Below is the running reslut for my implementation.
All threee tests failed.
![image](https://user-images.githubusercontent.com/97556577/155816993-5313501c-7d3a-46bb-a906-c3b05fa60aff.png)

Below is is the running result for the implmentation I reviewed, all three failed.
![image](https://user-images.githubusercontent.com/97556577/155817109-6cb522d4-b55c-4c4e-a995-463a37376391.png)

# 4. Answer to questions
1. I think there exist small codes that solve this problem. 
According to the VScode preview. Backticks can appears inside sqaure brackets or after paretheses. We can compare the index of backticks```'``` with ```[]``` to detect the posion of backticks relative to square brackets and paretheses to fix this problem.

2. I do not think there is a small codes can fix this problem. The reason is that there are three situations in snippet2. First one is ```[a [nested link](a.com)](b.com)``` which is a link inside another link. At this point, the inside link will be effective, the outside link should not be effective. Second```[a nested parenthesized url](a.com(()))``` should ignore the nest parentheses and print out the result as ```a.com(())```. Finally, ```[some escaped \[ brackets \]](example.com)``` a pair of brackets inside another pair of brackets shouold not effect the link. For these situations, i do not think there is a solution within 10 lines of codes.
3. I think there is a small code solution for snippet three. According to VScode preview, the newline inside brackets is not acceptable. However, a new line inside paretheses is acceptable. We just need to detect the index of ```\n``` and compare with the indx of bracket and paretheses. When printing the result, detlete the ```\n```.
