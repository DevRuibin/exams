1. Software Quality - Define aspects of software defects and defect management alterna-
   tives. Discuss different software quality characteristics and perspectives. Define correct-
   ness, reliability, safety and robustness.

    * What is a defect?
        - Some problems with the software, it can be an error, fault or failure.
        - Error: Human mistake when performing some software activities.
        - Fault: a defect in the software
        - Failure: a departure from the system's required behavior.
    * Defect management alternatives
        - Defect prevention: Prevent faults from being injected. (e.g. error blocking, error source removal)
        - Defect removal: Remove faults from the software. (e.g. inspection, testing)
        - Defect containment: Keep failures local, reduce failure impact. (e.g. fault tolerance, failure containment)
    * Software quality characteristics

      There are two perspectives of software:

        - Consumers:
            - Clients: pay for the software development
            - Customers: buy the software after it is developed
            - End users: use the software
        - Producers:
            - Developers: write the software
            - Testers

    So we need to discuss the quality characteristics from both perspectives.

    - From the user's perspective(external characteristics):
        - good enough for the price
        - Dependable: no defects, doing things right
        - Useful: serves the purpose, doing the right things
    - From the developer's perspective(internal characteristics):
        - good enough for the cost
        - Maintainable: easy to change, easy to understand, easy to test
        - interoperable: easy to integrate with other systems
        - modular: easy to understand, easy to change, easy to test, easy to reuse
    * Correctness, reliability, safety and robustness
        - **Correctness**: A program is correct if it is consistent with its specification. But it is seldom possible
          for
          a non-trivial program to be completely correct.
        - **Reliability**: the software does what it is supposed to do under certain conditions
          It is a likelihood of correct function for some unit of behavior. It is statistical approximation of
          correctness.
        - **Safety**: Prevents hazards.
        - **Robustness**: the software does not fail but behaves reasonably under extreme conditions.

2. Software development process - Define software verification and validation. Describe
   a software development process and how verification and validation activities fit into this
   process. Describe different types of software quality assurance activities.

    - **validation**: does the software system meet the user's real needs? Are we building the right system? Validation
      reflects the customer's needs.
    - **verification**: Does the software system meet the requirements? Are we building the system right? verification
      reflects a system conforms to its specification.
    - **software development process**: It is a set of activities, methods, practices, and transformations that people
      use to develop software.
        1. **Requirements**: what the system should do
        2. **Specification**: how the system should do it
        3. **Design**: how to build the system
        4. **Implementation**: building the system
        5. **Testing**: does the system meet the requirements?
        6. **Release**: deliver the system to the customer

      There are various models of software development process: waterfall, iterative, spiral, agile, XP, etc.

    - **How verification and validation activities fit into process.**

      Verification and validation activities are integrated info software stages of the software development process.
      Let us take the waterfall model as an example:
        - Requirements Gathering: verification ensures that the collected requirements are clearly defined, unambiguous
          and testable. Validation ensures that these requirements meet the needs and expectations of the stakeholders.
        - System Design: verification ensures that the design accurately implements the specified requirements and
          identifies potential design flaws. Validation ensures that design is sound, meets the user's needs and can
          effectively support the required functionality.
        - Implementation: Verification involves code review and other static analysis techniques to ensure that the code
          correctly implements the design and adheres to coding standards. Validation at this state typically involves
          unit testing to validate that individual components function correctly.
        - Testing: Verification in this phase includes ensuring that the testing procedures are correctly implemented,
          which validation involves system, integration and acceptance testing to ensure the software system functions
          are expected in an integrated environment.
        - Deployment: verification ensures the proper deployment of the software in the live environment. Valudation at
          this state checks that the system performs as expected in the live environment.

    - **Different types of software quality assurance activities.**
        - Testing: They are executed late in development, but we need to generate tests as early as possible.
            * Test generated independently of from the code, when the specifications are fresh in the mind of analysis
            * The generation of test cases may highlight inconsistencies and incompleteness of the corresponding
              specifications.
            * Tests may be used as compendium of the specifications by the programmers.
        - Inspection: It can be applied to essentially any document including requirements statements, architectural and
          detailed design documents, test plans and test cases and program source code.
            - The secondary befits are that spreading good practices and instilling shared standard of quality.
            - It takes a considerable amount of time and effort.
            - Re-inspecting a changed component can be expensive.
            - Used primarily where other techniques are inapplicable or where other techniques do not provide sufficient
              sufficient coveraeg.
        - Automatic static analysis
            - More limited in applicability. It is applicable to formal models, not to natural language documents.
            - It is applied when substituting machine cycles for human effort to make them more cost-effective.
        - Model checking
            - It exhaustively explores all possible states of a mode. It can be used to check state conditions, temporal
              logic and compare models.
        - Theorem proving: It is used to prove specifications and assumptions imply requirements. It can be implemented
          by using built-in thories, inference rules and decision procesures.

    - **Software analysis principles**
        - Partition
        - visibility
        - feedback
        - sensitivity
        - redundancy
        - restriction

3. Behaviour models - Define state models. Describe control flow graphs and their con-
   stituents. Describe call graphs and discuss context-sensitive analysis. Describe finite state
   machines and discuss abstraction.

    - **State models**: A model is an abstraction of the system. A state model is a model that describes the system in
      terms of its states and transitions between states.
    - **Control flow graphs**: A control flow graph is a directed graph that represents the flow of control in a
      program. It is a directed graph whose nodes are basic blocks and whose edges are control flow edges.
        - **Basic blocks**: It is a maximal program region with a single entry and single exit point. It often contains
          several statements. One statement can be splitted in several blocks.
        - **Edges**: It is a representation of almost all paths that might be traversed through a program during its
          execution. But it also ignores some flows which are called intra-procedural, e.g. exceptions, interrupts, etc.
        - **Nodes**: Represent regions of source code. They are connected by edges.
        - **Entry node**: It is the first node in the graph. It has no predecessors.
        - **Exit node**: It is the last node in the graph. It has no successors.
        - Linear code sequence and jump(LCSAJ): Sub-paths from one branching point to another(jumps).
    - **Call Graph**: Node represent procedures, like methods, functions and routines. Edges represent calls relation.
        - Context-sensitive call graph: It can keep track of the calling context, so it can infer that depends does not
          violate the calling context, such as bounds of array, etc. But it can grow exponentially with the depth of the
          calls.
    - **Finite state machines**:
        - Nodes: states(finite number)
        - Edges: transitions between states. They are labeled with events, conditions and operations.
        - Abstractions:
            - FSM accurately represents program behavior. if s -op-> s' is a transition in the program, then abstract(s)
              -op-> abstract(s') is a transition in the abstract FSM.

4. Data models - Define data dependence based on def-use pairs. Describe data dependence
   and control dependence graphs. Explain the general principle of dataflow analyses based
   on worklist algorithms, and the particular case of computing reaching definitions. Discuss
   the effect of pointers and procedures.
    - Data dependence: A def-use pair is a pair of statements in which the first statement defines a variable and the
      second statement uses the variable. A statement is data dependent on another statement if there is a def-use pair
      between them.

    - Data dependence graph: It is a directed graph whose nodes are program regions as in the control flow graph and
      whose enges are def-use pairs labelled with the variable name.
        - P2 depends on P1 iff data values used in P2 can be defined in P1.

    - Control dependence graph: It is a directed graph whose node are program regions as well and whose entry points to
      controlled blocks.
        - P2 depends on P1 iff P1 controls whether P2 executes. P1 is an entry point and P2 is any point.
        - *Program dependence: data or control dependence.*
      > Dominator: Node M is a dominator of node N iff every path from the root to N passes through M.
      >
      > Immediate dominator: Node M is an immediate dominator of Node N iff M dominates N and all other dominators of N
      dominate M.
      >
      > Each node except the root has a unique immediate dominator.

    - Data flow algorithm
        - Reaching definition:
          ```
          Let vd and ve denote the definitions of variable v at points d and e respectively, and u is a use of v.
          
          vd reaches u iff there is at least one control flow path from d to u and there is no intervenning definition of v on the path.
          
          ve kills vd iff it is on a control path from d
          
          (d, u) is a def-use pair of v iff vd reaches u.
          ```
        - Goal: compute the reaching definitions at node n. Suppose that node p is an immediate dominator of node n, if
          p can assign variable v, then vp reaches n. We say the definition vp is generated at p. iff a definition vd
          reaches p, and if v is not redefined at p, then vd reaches n.
            - Reach(n) = the set of definitions that reach n.
            - ReachOut(n) = the set of definitions that exit n.
          ```
          ReachOut(D) = (Reach(D) - Kill(D)) U Gen(D)
          ```
        - Worklist Algorithm
          ```
          foreach n in nodes do
            ReachOut(n) = {}
          end
          worklist = nodes;
          while worklist != {} do
            remove n from worklist;
            oldVal = ReachOut(n);
            Reach(n) = Union(ReachOut(p) for all p in pred(n));
            ReachOut(n) = (Reach(n) - Kill(n)) U Gen(n);
            if ReachOut(n) != oldVal then
             worklist = worklist U succ(n);
          end
          ```
          This algorithm is implemented using Python.
          See [worklist.py](https://github.com/DevRuibin/worklist_algorithm_for_reach)
        - Pointers
          Consider the following code:
          ```
          a[i] = 13;
          k = a[j];
          ```
          Are these two lines a definition-use pair? They are if the values of i and j are equal. but
          a static analysis cannot determine whether they are always, sometimes or never equal.

          We can see another example:
          ```
          int[] a = new int[3];
          int[] b = a;
          a[2] = 42;
          i = b[2];
          ```
          Here a and b are aliases, two different names for the same dynamically allocated array object.
          Dynamic references and the potential for aliasing introduce uncertainty into data flows analysis. The proper
          treatment of this uncertainty depends on the use to which the analysis will be put. For example, if we seek
          strong assurance that v is always initialized before it is used, we may not wish to treat an assignment to a
          potential alias of v as initialization, but we may wish to treat a use of potential alias of v as a use of v.
          A useful mental trick for thinking about treatment of aliases is to translate the uncertainty introduced by
          aliasing into uncertainty introduced by control flow.

          For example:

          ```
          a[i] = 13;
          k = a[j];
          ```

          We can image replacing this by the equivalent code:

          ```
          a[i] = 13;
          if(i==j){
              k = a[i];
          }else{
              k = a[j]
          }
          ```

          In the transformed code, we could treat all array references as distinct, because the possibility of aliasing
          is fully expressed in control flow. Now, if we using an any-path analysis like reaching definitions, the
          potential aliasing will result in creating a definition-use pair. On the other hand, an assignment to a[j]
          would not kill a previous assignment to a[i]. This suggests that for any-path analysis, gen sets should
          include everything that might be referenced, but kill sets should include only what is definitely referenced.

          For all-paths analysis, gen sets should include only what is definitely referenced, but kill sets should
          include all the possible aliases.

          But sometimes, it is sufficient to treat all nonlocal information as unknown. For example, we could treat two
          instances of a same object as potential aliases of each other.

        * Procedures

          Reach, Avail, etc. are flow-sensitive, intra-procerual analyses. O(n^3) for one procedure

          Flow-sensitive, interprocedural analyses' time complexity is O(n^3) on the whole program.

          Many interprocerual flow analysies are flow insensitive. Often is good enough, e.g. type checking.

            - Context-sensitive: distinguishes sub() called from foo() and from sub() called from bar()
            - Context-insensitive analysis does not separate them, as if foo() could call sub() and sub() could then
              return to bar().

          What is intraprocedural? It is withing a single method or procedure.

          What is interprocedural? it can be across several methods or procedures.

5. Functional testing - Define test case, test obligation, adequacy criterion, test satisfaction.
   Define functional and structural testing. Explain category-partition testing. Explain pair-
   wise and n-wise testing. Explain catalog-based testing.

    1. Test case: a set of inputs, execution conditions and a pass/fail criterion.

    2. Test suite: a set of test cases.

    3. Test or test execution: the activity of executing test cases and evaluating their results.

    4. Test case specification: a requirement to be satisfied by one or more test cases.

    5. Test obligation: a partial test case specification, requiring some property deemed important to through testing.

       > a test obligation is a high-level requirement that focuses on important properties or aspects of the system to
       be tested, while a test case specification provides detailed instructions for executing individual test cases,
       including specific inputs, expected outputs and test steps.

    6. Adequacy criterion: A test adequacy criterion is a predicate that is true or false of a <program, test suite>
       pair. The adequacy criterion is then satisfied if every test obligation is satisfied by at least one test case in
       the suite and all the tests succeed.

    7. Functional testing:  It is as known as black box testing or closed box testing. The program content is unknown or
       ignored. We only care the pair of input and output.

    8. Structural testing. It is as known as white box or clear box as the program content is visible and observed. The
       need to care the internal operations.

    9. Category-partition testing: it separate the input space into classes whose union is the entire space. Every class
       covered by at least one test case. Because we believe that each fault leads to failures are dense in some class.
       The ideal situation is that all points in some classes produce the failure. As for category-partition testing,
       the category refers to the method of partition the class which is one class per category of behavior.

        1. Decompose the specification into units, parameters and categories.
            1. Identify independently testable units
            2. For each unit, identify parameters and environment elements.
            3. For each parameter, identify categories.
        2. Identify relevant choices for each category.
            1. Identify classes of values for each category
            2. boundary value testing
            3. Erroneous condition testing
        3. Introduce constraints.
            1. A combination of values for each category. But if we just use a cross join, it will be very large which
               is impossible. So we introduce constraints to rule out impossible combinations and reduce the size of the
               test suite if it is too large.

    10. Pairwise testing

    It is a kind of category-partition testing but it uses a different methods when introducing constraints which is
    called pairwise combination. It generate combinations that efficiently cover all pairs of choices. Because most
    failures are triggered by single values or combinations of a few values.

    11. N-way wise testing: similar to pairwise testing. Instead of focusing solely on pairs of parameters, N-way
        testing aims to create test cases that cover all possible combinations of values for a specified number of
        parameters (often denoted as "t"). This type of testing is often used when the number of inputs to the system is
        relatively small, but there are too many combinations to test exhaustively.

    12. Catalog-Based Testing: It is better that human judgment is used when deriving values classes. The catalog lists
        important cases for each possible type of variable.
        for example: integer variables:
        1. The element immediately below the lower bound
        2. The lower bound
        3. A non-boundary value within the interval
        4. etc.

        It can speed up the test design process, rountinize many decisions, better focusing human effort, and a
        accelerate training and reduce errors.

        Steps:
        - Analyze the initial specification to identify simple elements, such as: preconditions, postconditions,
          definitions,
          variables and operations.
            - Pre-conditions: the conditions that must be true before the operation is executed.
            - Post-conditions: result of the operation.
            - variables: elements used for the computation.
            - Operations: main operations on variables and inputs.
            - Definitions: abbreviations used in the specification.
        - Derive a first set of test case specifications from pre-conditions, post-conditions and definitions.
            - Validate preconditions. Such as inputs satisfy the preconditions.
            - Assumed precondition: our inputs do satisfy the preconditions.
        - Complete the set of test case specifications using test catalogs.
            - For each element of the catalog, apply the catalog entry to all matching specification.
            - Delete redundant test cases.

6. Structural testing - Define statement, branch and condition coverage, compound condi-
   tions and MC/DC, and compare their strengths. Define path coverage, discuss limitations
   and show some practical path coverage criteria. Define data flow coverage criteria. Discuss
   the problems of aliases and infeasibility.

7. Model-based testing - Explain the principles of model-based testing. Explain path-
   insensitive and path-sensitive state machine coverage criteria. Discuss coverage criteria for
   decision structures and grammars.

8. Object-oriented testing - Explain the principles of testing of object-oriented software, at
   the unit and integration level. Discuss structural coverage criteria for intra- and inter-class
   testing. Discuss the issues of test oracles, polymorphism and exception handling.

9. Fault-based testing - Explain the principles and assumptions of mutation testing. Give
   examples of mutation operators. Discuss fault-based coverage measures. Discuss ways
   to reduce the cost of mutation testing. explain fault estimation using seeded faults or
   independent test groups.

10. Test execution I - Describe the principles of scaffolding for test execution. Discuss
    different types of test oracles. Describe the nature and objectives of unit and integration
    testing activities. Discuss and compare different integration testing strategies.

11. Test execution II - Describe the nature and objectives of system, acceptance and regres-
    sion testing activities. Explain regression test selection and prioritization.

12. Symbolic execution - Describe the principles of symbolic program execution. Describe
    the principles of program verification using symbolic execution. Discuss contract-based
    reasoning on procedures and data structures.

13. Program analysis - Describe the principles of program inspection, static and dynamic
    program analysis. Explain symbolic testing and its application to pointer analysis. Explain
    dynamic analysis and its application to lockset analysis.

14. Finite state analysis I - Describe the principles of finite-state analysis. Define safety and
    liveness properties and discuss their verification. Discuss the model size and correspondence
    problems.

15. Finite state analysis II - Explain intensional representations for finite state analysis and
    describe the use of binary decision diagrams. Discuss iterative model refinement. Describe
    the principles of data model verification.

16. Software measurement: size - State the general principles of software measurement.
    Discuss size measurement metrics based on lines of code. Explain functional size measure-
    ment using function points.

17. Software measurement: structure - Describe the principles of structure measurement.
    Describe hierarchical measures based on prime decomposition of control flow graphs. Define
    cyclomatic complexity measure. Discuss design-level, inter-modular complexity measures.

18. Software measurement: quality - Describe the principles and elements of quality
    models. Discuss defect-based quality measures. Discuss usability, maintainability and
    security measures.

19. Software reliability - Describe the model of reliability based on failure rates. Define
    failure probability functions, reliability, maintainability, availability, MTTF and MTTR.
    Describe the case of constant failure rates.

20. Failure prediction - Describe the principles of failure prediction systems. Discuss the
    example of the Jelinski-Moranda model. Discuss statistical testing.