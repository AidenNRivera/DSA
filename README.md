# DSA

Project One: A vector works well when the dataset is small to medium and mostly read-only. Printing all courses in sorted order is efficient if you sort once with a good algorithm (O(n log n)), but looking up a single course requires a linear O(n) search.

A hash table excels at single-course lookups, with average-case O(1) performance for inserts and searches. The drawback is that it doesn’t maintain order, so printing courses alphanumerically requires an extra sort step (O(n log n)). It also has slightly higher memory overhead due to buckets and collisions.

A binary search tree (BST) balances both needs. A balanced BST provides O(log n) insertions and lookups, and its in-order traversal produces a sorted list in O(n) without additional sorting. The main risk is that a naive BST can degrade to O(n) operations if it becomes unbalanced, but that can be avoided.

Project Two: 
// print an alphanumeric list of all CS and MATH courses
static void printCourseListCS(const BST& tree) {
    vector<Course> all;
    tree.inorder(all);
    cout << "\nHere is a sample schedule:\n\n";
    for (const auto& c : all) {
        if (isCSorMath(c.id)) {
            cout << c.id << ", " << c.title << "\n";
        }
    }
    cout << "\n";
}

**1. What was the problem you were solving in the projects for this course?**
   The problem I was solving was how to efficiently store, search, and display course data for an advising program. The program needed to allow users to load data from a file, look up individual courses, and print    out a full list of courses in alphanumeric order.
**2. How did you approach the problem? Consider why data structures are important to understand.**
   I approached the problem by comparing different data structures, which are vectors, hash tables, and binary search trees. Each had strengths and weaknesses, but the BST was the best fit because it supports efficient lookups while also producing a sorted list through in-order traversal. This showed me why understanding data structures is important, the right data structure makes a program both faster and easier to manage.
**3. How did you overcome any roadblocks you encountered while going through the activities or project?**
   One roadblock I faced was handling inconsistent input, like extra spaces or lowercase course IDs, which caused searches to fail. I overcame this by writing helper functions such as trim() and upper() to clean the data before storing it in the BST. Another challenge was making sure the traversal printed results in the correct order, which I solved by carefully testing the BST’s recursive in-order function.
**4. How has your work on this project expanded your approach to designing software and developing programs?**
   This project expanded my approach by showing me how important planning is before coding. Instead of jumping straight into writing functions, I had to think about data flow, efficiency, and how the user would interact with the program. It made me realize that choosing the right design early on saves time and prevents problems later on.
**5. How has your work on this project evolved the way you write programs that are maintainable, readable, and adaptable?**
   My work on this project has made me more consistent about writing clean and maintainable code. I used clear variable names, inline comments, and error handling to make the program easier to read and update. I also wrote functions in a way that could be reused, like the BST operations and input helpers. This helped me build habits that will carry over into future projects where readability and adaptability are just as important as getting the program to run.
