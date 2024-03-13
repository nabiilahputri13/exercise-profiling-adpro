# TUTORIAL 5

Screenshots
-----------

### all-student-name

<img width="1280" alt="Screenshot 2024-03-12 235634" src="https://github.com/nabiilahputri13/inventory/assets/124870275/b0f5c4c1-8f9e-454f-adc3-85044088e167">
<img width="1280" alt="Screenshot 2024-03-13 000630" src="https://github.com/nabiilahputri13/inventory/assets/124870275/01eb4d30-51cd-4d24-9fb9-33257d654c94">

### highest-gpa

<img width="1280" alt="Screenshot 2024-03-12 235711" src="https://github.com/nabiilahputri13/inventory/assets/124870275/966e50c2-9eec-4408-be71-81807628ba01">
<img width="1280" alt="Screenshot 2024-03-13 000236" src="https://github.com/nabiilahputri13/inventory/assets/124870275/3011c7bf-6e56-43b6-9ce9-b64bf4cce495">

Reflection
----------

1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?
2. How does the profiling process help you in identifying and understanding the weak points in your application?
3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?
4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?
5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?
6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?
7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?

Reflection Answer
-----------------
1. Performance testing with JMeter evaluates application performance under various loads, focusing on overall behavior. Profiling with IntelliJ delves deep into code execution, uncovering specific bottlenecks for optimization. JMeter simulates user interactions, while IntelliJ analyzes runtime behavior for detailed insights. Both tools complement each other, aiding in comprehensive performance optimization.
2. Profiling helps by pinpointing performance bottlenecks, memory leaks, concurrency issues, inefficient I/O operations, and excessive object allocation. It offers detailed insights into code execution, enabling targeted optimization efforts for improved application performance and stability.
3. Yes, IntelliJ Profiler is effective in assisting with the analysis and identification of bottlenecks in application code. It provides detailed insights into various aspects of runtime behavior, including CPU usage, memory allocation, thread activity, and method execution times. By visualizing these metrics and highlighting performance hotspots, IntelliJ Profiler helps developers pinpoint areas for optimization and improve overall application performance.
4. The main challenges faced during performance testing and profiling include:

- Complexity of Systems: Modern applications often consist of intricate architectures with numerous components interacting in complex ways. Testing and profiling such systems require a deep understanding of their structure and behavior.
- Large Data Sets: Testing and profiling large-scale applications with massive data sets can be resource-intensive and time-consuming. Analyzing extensive data can also pose challenges in identifying meaningful insights.
- Realistic Simulation: Creating realistic test scenarios that accurately mimic user behavior and system loads can be challenging. Simulating diverse user interactions and load patterns requires careful planning and consideration.
- Overhead: Introducing testing and profiling tools into the application stack can introduce overhead and affect performance metrics. Minimizing this overhead while still capturing relevant data is crucial for accurate analysis.
- Intermittent Issues: Some performance issues may only manifest under specific conditions or intermittently, making them difficult to reproduce and diagnose.

To overcome these challenges:

- Comprehensive Testing Strategy: Develop a comprehensive testing strategy that includes a mix of load, stress, scalability, and endurance testing to cover various aspects of application performance.
- Effective Monitoring: Implement effective monitoring solutions to continuously track application performance in real-time. This helps identify performance degradation or anomalies as they occur.
- Automation: Automate testing and profiling processes as much as possible to streamline workflows and reduce manual effort. Utilize tools and frameworks that support automation and integration with CI/CD pipelines.
- Profiling Tools: Use advanced profiling tools that offer detailed insights into application behavior while minimizing overhead. Experiment with different profiling techniques and settings to balance accuracy and performance.
- Collaboration: Foster collaboration between development, testing, and operations teams to ensure a holistic approach to performance optimization. Regular communication and knowledge sharing help identify and address issues more effectively.
5. The main benefits of using IntelliJ Profiler for profiling application code include detailed insights into runtime behavior, identification of performance bottlenecks, efficient memory management, precise method-level analysis, and seamless integration with development workflows.
6. Cross-Validation: Validate results by cross-referencing findings from both tools and analyzing discrepancies. Look for patterns or commonalities to identify potential root causes.
Root Cause Analysis: Investigate further to determine the underlying reasons for discrepancies. This may involve manual inspection of code, additional profiling, or deeper performance testing.
Collaboration: Foster collaboration between teams involved in testing and development. Share findings and insights to gain a comprehensive understanding of performance issues and their implications.
Iterative Optimization: Use findings from both tools iteratively to refine performance optimization efforts. Address discrepancies by prioritizing areas identified by both JMeter and IntelliJ Profiler for improvement.
7. I changed 
- getAllStudentsWithCourses(): (Previously, it fetched all students and then queried for their courses one by one. Now, it directly returns all student courses from the repository.)
- joinStudentNames(); (Previously, it iterated over all students to concatenate their names into a string. Now, it uses Java 8 streams to map student names and join them using Collectors.joining().)
in StudentService.java
These changes aim to improve performance by reducing database queries and leveraging Java 8 features for more concise and efficient code. 

and
highestGpa(): (Previously, it directly returned the toString() representation of the Optional<Student> object. Now, it checks if the Optional<Student> is present and returns the student's details if available, or "Empty" if not.)
in Student Controller.java

These changes ensure that the /highest-gpa endpoint handles the case when no student with the highest GPA is found. By returning "Empty" in such cases, it provides a more informative response to the client.

To ensure that changes made to the application code do not affect its functionality, I followed
- Unit Testing: Develop and execute comprehensive unit tests for each component and functionality of the application. Ensure that unit tests cover both positive and negative scenarios, including edge cases and error conditions. Run unit tests frequently to catch any regressions introduced by code changes.
- Integration Testing: Conduct integration testing to verify that different components of the application work together as expected. Test interactions between modules, APIs, and external dependencies to ensure that changes do not disrupt the overall functionality of the application.
- Regression Testing: Perform regression testing to validate that existing features and functionalities continue to work correctly after making changes. Re-run existing test cases and compare results to ensure that there are no unintended side effects or regressions introduced by code modifications.
- Code Reviews: Conduct thorough code reviews to ensure that code changes adhere to coding standards, best practices, and design principles. Involve peers or senior developers in code reviews to provide feedback, identify potential issues, and validate changes against functional requirements.
- Continuous Integration (CI): Utilize CI/CD pipelines to automate the process of building, testing, and deploying the application. Configure CI pipelines to run automated tests, including unit tests, integration tests, and regression tests, for every code commit or pull request. This ensures that changes are validated early and consistently throughout the development lifecycle.
- Monitoring and Observability: Implement monitoring and observability solutions to track application performance, health, and error rates in real-time. Monitor key metrics, logs, and alerts to detect any anomalies or issues introduced by code changes. Use monitoring tools to identify and troubleshoot issues promptly.
- Rollback Plan: Have a rollback plan in plae to revert changes quickly in case of unexpected issues or regressions. Maintain version control and rollback mechanisms to rollback to a stable state if necessary. Test rollback procedures in advance to ensure they work effectively when needed.
