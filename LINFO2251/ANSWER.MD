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
        - Deployment: verification ensures the proper deployment of the software in the live environment. Validation at
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
              coverage.
        - Automatic static analysis
            - More limited in applicability. It is applicable to formal models, not to natural language documents.
            - It is applied when substituting machine cycles for human effort to make them more cost-effective.
        - Model checking
            - It exhaustively explores all possible states of a model. It can be used to check state conditions,
              temporal logic and compare models.
        - Theorem proving: It is used to prove specifications and assumptions imply requirements. It can be implemented
          by using built-in theories, inference rules and decision procedures.

    - **Software analysis principles**

        - Partition
        - visibility
        - feedback
        - sensitivity
        - redundancy
        - restriction

3. Behavior models - Define state models. Describe control flow graphs and their constituents. Describe call graphs and
   discuss context-sensitive analysis. Describe finite state machines and discuss abstraction.

    - **State models**: A model is an abstraction of the system. A state model is a model that describes the system in
      terms of its states and transitions between states.
    - **Control flow graphs**: A control flow graph is a directed graph that represents the flow of control in a
      program. It is a directed graph whose nodes are basic blocks and whose edges are control flow edges.
        - **Basic blocks**: It is a maximal program religion with a single entry and single exit point. It often
          contains several statements. One statement can be splitted in several blocks.
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
       modular
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

    1. Structural testing: requires that all paths are tested. The test criteria are based on the
       structure of the program.
    2. statement coverage:  it measures the number of executed statements in the source code out of the total
       statements. The aim is to ensure that every line of code in the program has been executed at least once.
    3. branch coverage: This type of testing goes a step beyond statement coverage. In addition to ensure that each line
       of code has been executed, branch coverage tests each decision point in the source code. This ensure that both
       the true and false branches have been executed at least once.
    4. condition coverage; This extends branch coverage by ensuring that each Boolean expression expression has been
       evaluated both to true and false.
    5. compound condition and MC/DC coverage: Compound conditions are conditions with multiple Boolean expressions.
       MC/DC is a testing strategy that goes further than condition coverage by ensuring that each condition in a
       decision has been tested for tru and false, and that each condition independently affects the outcome of the
       decision.
    6. path coverage: This type of testing considers all possible paths that can be taken in the source code.
        1. path coverage measure: C = (P / T) * 100%
            - C: path coverage
            - P: number of executed paths
            - T: total number of paths
        2. There are more paths than branches. The problem is that the number of paths grows exponentially with the
           number of branches. So it is impossible to test all paths.
        3. path coverage criteria:
            - all paths: test all paths
            - partition infinite set of paths into finite number of classes, by limiting the number of traversal of
              loops, the length of the paths to be trancersed and the dependencies among selected paths.
            - boundary interior path coverage: each path up to the first repeated node must be executed at least once.
            - Loop boundary coverage: each loop body must be iterated zero times, one time and more than one time at
              least once.
    7. data flow coverage: The intuition is statements interact through data flow, value computed in one statement and
       used in another. A bad value computation revealed only when it is used.
        - All DU pairs: Each DU pair is exercised at least once.
        - All DU paths: Each simple(non looping) DU path is exercised at least once.
        - All definitions: For each definition, some DU pair is exercised at least once.
        - Arrays and pointer are critical for data flow analysis.
            - under-estimation of aliases -> some DU pairs are missed
            - Over-estimation of aliases -> may introduce infeasible paths.

7. Model-based testing - Explain the principles of model-based testing. Explain path-
   insensitive and path-sensitive state machine coverage criteria. Discuss coverage criteria for
   decision structures and grammars.

    1. principle: Devise test cases to check actual behavior against behavior specified by the model. The coverage is
       similar to structural testing, but applied to specification and design models.
    2. State coverage: every state in the model should be visited at least once.
    3. Transition coverage: every transition in the model should be visited at least once.
    4. Path insensitive: Transition coverage assumes that transitions depend only on current state, note on path to
       reach the state.
    5. Path sensitive: Transition coverage assumes that transitions depend on the path to reach the state.
    6. path sensitive criteria:
        - Single state path coverage: Traverse each subpath that reaches states at most once.
        - Single transition path coverage: Traverse each subpath that reaches thrasitions at most once.
        - Boundary interior loop coverage: Traverse each distinct loop the minimum, an intermediate and the maximum or a
          large number of times.
    7. Decision structure coverage: The coverage of decision structures is based on the decision outcomes.
        1. Basic condition coverage: a test case for each column
        2. Compound condition coverage: a test case for each possible combination of basic conditions.
        3. Modified condition/decision coverage: add columns that differ in one input row and in outcome, merge
           compatible columns. A test case specification for each column.
    8. Grammar based testing
        1. Test cases and strings are generated from the grammar
        2. Production coverage: each production must be used at least once.
        3. Boundary condition coverage: each recursive production must be used (min, min+1, max-1, max) times.
   9. Grammar vs. Combinatorial testing
       1. combinatorial testing: good for mostly independent parameters. A few constraints are ok, but complex
          constraints are hard.
       2. Grammar testing: good for sequences and nested structure. Relations among different parts may be difficult to
          describe and exercise systematically.
8. Object-oriented testing - Explain the principles of testing of object-oriented software, at
   the unit and integration level. Discuss structural coverage criteria for intra- and inter-class
   testing. Discuss the issues of test oracles, polymorphism and exception handling.
    1. object-oriented testing: For an object software:
        - unit: single class
        - unit testing: intra-class testing
        - integration testing: inter-class testing
    2. intra-class testing:
        - basic idea:
            - Object have a state
            - Methods calls are state transitions
            - Test cases are sequences of method calls.
            - The state machine can be derived from specification and code.
        - Intra-class structural testing:
            - As for procedural software, start with functional testing, then complete with structural testing.
            - Use control flow graph: each metho + node for class = edges -> method, method -> class => control flow
              graph.
    3. Inter-class testing:
        - basic idea:
            - test interaction between classes
            - bottom-up integration, according to "depends" relation.
            - use/include hierarchy:
                - A uses B: A makes method calls on B
                - A includes B: A objects include reference to B objects ignore inheritance, abstract classes.
            - Bottom-up integration, clustering.
        - Inter-class structural testing: DU pair structural testing:
            - Working bottom-up in dependencies hierarchy
            - inspectors:
                - inspectors: use, but do not modify object state.
                - modifiers: modify, but no use object state.
                - inspector/modifiers: bot use and modify object state.
                - treating a whole object as variable.
                - Treat inspector calls as uses and modifier calls as defs.
    4. Test oracles:
        - Test oracles must be able to check the correctness of a test execution
            - correct output: ok, can be checked
            - correct new state: not accessible, encapsulation
        - Accessing the state:
            - Intrusive approach: use language constructs(C++ friend classes), add inspector methods. -> breaks
              encapsulation, may produce undesired results.
            - Equivalent scenarios approach: generate equivalent sequences of methods calls, compare the final states of
              the objects.
    5. Polymorphism: Combinatorial explosion problem. When testing a child class, we would like to test only what is
       needed not what has been tested in parent classes.
        - Track test suites and test executions
            - determine which new tests are needed.
            - determine which old tests must be re-executed.
        - New and change behavior
            - New methods must be tested
            - Re-defined methods must be re-tested, but we can partially reuse the test suites.
            - unchanged methods need not be re-tested.
        - Executing test cases is usually cheap, it may be simpler to re-execute the full parent test suite.
    6. Exception handling:
        - Exception: implicit control flows and they may be handled by different hanlers.
        - Impractical t treat exceptions like normal flow, as there are every test exception source times every test
          exception handler.
        - Program error exceptions: test to prevent them from happening instead of handling them.
        - Explicit throws: test with respect to every handler on call stack.
        - Local exception handlers: test the exception handling code.
        - Non-local exception handlers: difficult to determine all <source, handler> pairs.
            - Design rule: if a method propagates an exception, the method call should have no other effect.
            - test all sources, all handlers but not all pairs.
9. Fault-based testing - Explain the principles and assumptions of mutation testing. Give
   examples of mutation operators. Discuss fault-based coverage measures. Discuss ways
   to reduce the cost of mutation testing. explain fault estimation using seeded faults or
   independent test groups.
    1. Principles: a mutation is a syntactic change, for example, change a + b to a - b.
        - A mutant is a copy of a program with a single mutation.
        - Run test suite on all the mutants
        - A mutant is killed if the fails on at least one test case.
        - If many mutants are killed then the test suite is effective at finding real faults.
    2. Assumptions:
        - Competent program hypothesis: Programs are assumed to be nearly correct. Real faults are small variations from
          the correct program. Mutants are reasonable models of real real faults.
        - Coupling effect hypothesis: Tests that find simple faults also find more complex faults. Even if mutants are
          only only simple faults, a test suite that kills mutants is good at finding complex faults too.
    3. examples:
        - crp: constant for constant replacement: replace a constant by another constant.
        - ror: relational operator replacement: replace a relational operator by another one. x <= 5 => x < 5
        - vie: variable initialization elimination: remove initialization of a variable.
    4. Mutation analysis:
        - steps: select mutation operators, generate mutants and distinguish mutants.
        - Mutation score: number of killed mutants / number of mutants.
        - Mutation score is a measure of test suite effectiveness.
        - How mutants survive:
            - The mutant is equivalent ot the original program.
            - the test suite is inadequate.
              Adding a test case for just this mutant is a bad idea. We care about the real bugs, not the fakes.
    5. discuss ways to reduce the cost of mutation testing
        1. Equivalent mutants are hard to determine and there are lots of mutants.
            - high cost
            - grows with the square of the program size.
            - running each test case on each mutant is expensive.
        2. Weak mutation: observe states of program and mutant, kill as soon as a difference is found
        3. Meta mutant: mutant with several seeded faults, with mechanism to activate them. Check several mutants at
           once.
        4. Statistical mutation: create a random sample of mutants.
        5. Fault estimation:
            - seeded faults: inject faults into the program, run test suite, count the number of faults found.
                1. Intentionally seed S faults into the program.
                2. Run the tests. s discovered seeded faults and n discovered natural faults.
                3. Hypothesis: n / N = s / S
            - independent test groups: run test suite on each group of faults, count the number of faults found.
                - It is used when we don't know typical faults.
                - split tests in two groups E1 and E2
                - n1 faults detected by E1
                - n2 faults detected by E2
                - n12 faults detected by both E1 and E2
                - N faults in the program
                - Hypothesis: n1 / N = n12 / n2
10. Test execution I - Describe the principles of scaffolding for test execution. Discuss
    different types of test oracles. Describe the nature and objectives of unit and integration
    testing activities. Discuss and compare different integration testing strategies.
    1. Scaffolding: code produced to support development activities especially testing. Not part of the product. May be
       temporty.
        - Test harness: envrionment in which the component is tested. for example: Software simulation of a hardware
          device.
        - Test driver: calls the component. Applies the test cases. A main program for running a test.
        - Test stubs: called by the component. Substitutes for the called components.

       The scafolding must provide:
        - Controllability: allow to execute test cases.
        - Observability: allow to judge the outcome of the test.
    2. Different types of test oracles:
        - Did the test case succeed or fail? Oracle: software that determines whether a test passed or failed.
        - Better than manual checking. More efficient, reliable and capable(large data sets).
    
       Oracles should ideally report Pass for all executions and may report PASS for some incorrect executions.
    
       1. Comparison-Based Oracle: Oracle compare actual to expected output, reports if (actual == expected) then pass else fail. Fine
          for a small number of hand-generated test cases. E.g. JUnit.
       2. Self-Checked as oracle: Oracle as self-checks in the program judge correctness. E.g. assert in Java.
          Usable with large, automatically generated test suites. Often only a partial check.
          
          For example, there is a test case for quick sort, the self-check is to check if the array is sorted, but it does not check the items in the array.
       3. Assertions as oracle:
          - Invariants on data structures e.g. assert 0 <= size size <= a.length.
          - Pre- and Post-conditions: e.g. assert k!=null; v= dict.get(k); assert dict.contains(k, v)
          - may need to deal with quantifiers. Implement as iteration => does not scale well or sample some elements.
       4. Capture and Replay: 
          - Capture: a manually run test case, sequence of inputs and outputs.
          - Replay: it automatically wit a comparison-based oracle and compare actual to captured output.
    3. Unit testing: AKA module testing, component testing
       
        - Testing: feed inputs, check valid outputs
        - Code review, analyses: check internal data structures, logic.
    4. Integration testing: Assemble components together and check correct interaction.
    5. Function Testing: The whole system. Check that the behavior conforms to functional requirement specifications.
    6. Performance Testing: The whole system. Check that the behavior conforms to non-functional requirement specifications.
    7. Acceptance Testing: The whole system. Check that the behavior conforms to the customer requirement documentation.
    8. Regression Testing: 
       - Regression = loss of correct functionality after a change, like adding new features, changing existing features, fixing bugs.
       - Regression testing: re-executing tests after any change to detect regressions.
       - Can be a major cost of software maintenance, sometimes much more than making the change.
    9. Discuss different integration testing strategies:
       Integration testing is a phase in software testing in which individual software modules are combined and tested as a group. It's conducted to expose defects in the interaction between integrated units. The aim is to ensure that, together, the different parts of the software operate correctly. Below are some common strategies for integration testing:
    
       - Big Bang Approach: In this strategy, all the modules are integrated together and tested as a whole. The advantage is that everything is tested thoroughly in one cycle, but the disadvantage is that isolating defects can be very challenging because everything is tested together.
    
       - Top-Down Approach: This approach begins with high-level modules and incrementally incorporates lower-level modules. Stubs, which are dummy modules, are used to simulate lower-level modules that are not yet integrated. This approach is beneficial as it allows early observation of high-level functionality. However, the need for many stubs may be a drawback.
    
       - Bottom-Up Approach: This approach starts with the low-level modules and progresses to higher-level modules. Drivers, which are dummy modules, are used to simulate higher-level modules. The advantage is that the detailed functionalities are tested thoroughly, but the drawback is that the higher-level overview is not available until later in the process.
    
       - Sandwich (or Hybrid) Approach: This strategy is a combination of top-down and bottom-up approaches. The system is viewed as having three layers: top, middle, and bottom. The top-down approach is used for the top and middle layers, and the bottom-up approach is used for the middle and bottom layers. The advantage is that it utilizes the benefits of both top-down and bottom-up approaches.
    
       - Incremental Integration Testing: In this strategy, the modules are integrated and tested one at a time. The benefits include the ease of isolating errors and the ability to do regression testing every time a new module is added. The disadvantage is that it requires a lot of time and resources, as it involves multiple stages of integration and testing.

11. Test execution II - Describe the nature and objectives of system, acceptance and regres-
    sion testing activities. Explain regression test selection and prioritization.

    1. System testing: System testing is a level of software testing where the complete and integrated software system
       is tested. It verifies that the system meets its requirements as a whole and checks
       both the functional and non-functional aspects of the system. This level of testing is important because it
       checks end-to-end working of the software and validates
       whether the system behaves as expected or not. The main goal is to evaluate the system's compliance with the
       specified requirements.
    2. Acceptance testing: Acceptance testing is a leve of software testing where a system is tested acceptability. The
       purpose of this test is to evaluate the system's compliance
       with the business requirements and to assess whether it is ready for delivery or not. User Acceptance Testing is
       one of the most common types of acceptance testing, where the users test the software to make sure it can handle
       required tasks in real world scenarios, according to specifications. Acceptance testing has a user-centric focus
       and the primary aim is to build confidence in the system and gain customer approval.
    3. Regression Testing: Regression Testing is a type of testing carried out to ensure that changes have not
       introduced new faults in existing developed software. It is performed after modification of a system, comonent,
       or a group of related measures. Regression testing ensures that previously developed and tested software still
       functions the same way after it is interfaced with new or altered components. Its primary objective is to catch
       defects that may have been inadvertently intriduced into a new build or release.
    4. Explain regression test selection
        - Test case selection: do not execute some test cases when test cases are expensive to execute. Execute only
          test cases related to elements that were affected by the change.
        - Code-based selection: only execute test cases that execute changed or new code. Independent: a test case can't
          find a fault in code it does not execute.
        - Specification-based selection: only execute test cases that test new and changed functionality. Independent: a
          test case that is not for a changed feature X might find a but in feature X.
    5. Regression prioritization:
        - Execute some test cases less often when a very large test suite can't be executed every day.
        - Basic idea:
            1. Execute all test cases, eventually
            2. Execute some sooner than others.
        - Possible priority schemes:
            1. Specification-based: priority to test cases related to changed and added features.
            2. Round robin: Priority to least-recently-run test cases.
            3. Track record: Priority to test cases that have detected faults before. They probably execute code with a
               high fault density.
            4. Structural: Priority to executing elements that have not been recently executed.

12. Symbolic execution - Describe the principles of symbolic program execution. Describe
    the principles of program verification using symbolic execution. Discuss contract-based
    reasoning on procedures and data structures.

    Execute the program with symbolic values. Variables receive symbolic values. execution paths accumulate symbolic
    conditionss -> bridges program behavior to logic.
    1. Values are symbolic expressions
    2. Executing statements computes new expressions
    3. For branching statements, both brnaches are possible. Need to record the condition for the execution of each
       branch.
    4. Path accumulate conditons which may become extremely complex. We can simplify it by replacing a complex
       conditions P with a weaker W such that P => W. W des
       describes the path with less precision. (W is a summary of P)
    5. To reason about program behavior in a loop, we can plave an invariant. Each time program execution reaches the
       invariant W, we can weaken the execution conditon P to w
        - Check that P => W
        - Substitute W for P
    6. If:
        - Every loop contains an invariant
        - There is an assertion at the beginning of the program
        - There is an assertion at the end of the program

         Then every possible execution path is a sequence of segments from one assertion to the next.
         
            - Precondition: assertion at the beginning of a segment
            - Postcondition: assertion at the end of the segment
    
     Describe the principles of program verification using symbolic execution
    
    1. verify for each basic path
       1. Starting from the precondition
       2. Execute the program segment
       3. The post-condition holds at the ends.
    2. Then the execution of any path is correct
    
    Discuss contract-based reasoning on procedures and data structures.
    
     - On Procedure: Compositional reasoning. Follow the hierarchical structure of a program:
       - at small scale within a single procedure
       - at large scale (across multiple procedures)
       - Hoare triple: [pre] block [post]
            - if pre is satisfied at the entry to the block, then the post should be satisfied after execution of the block.
            - summarize the effect of a block of program by a contract
            - Prove that block satisfies pre/post then use the contract wherever the block is used.
     - On data structure: Data structure module = data + operations = variables + procedures
       - Contract 
         - Abstraction function "abs": relates data structures D to an abstract model D'. Like Directory -> <key, value> map
         - Structural invariant 'ok': data structure characteristics that must be maintained. Dictionary -> OK. For each key, there is at most one value.

13. Program analysis - Describe the principles of program inspection, static and dynamic
    program analysis. Explain symbolic testing and its application to pointer analysis. Explain
    dynamic analysis and its application to lockset analysis.
    1. Describe principles of program inspection:

       Systematic, detailed review of artifacts to find defects and assess quality.

        1. Find and remove defects
        2. Incentive to produce good code
        3. Share coding norms and practices
        4. Familiarize new staff with the code

       Team: the programmers + experts + checklist

       With different perspectives: junior and senior engineers, test, mangers, analysts and architects.

       Moderator: external senior manager.
    2. Static program analysis: examine source code. Examine the complete execution space but may lead to false alarms.
    3. Dynamic program analysis; examine execution traces. No infeasible path problem but can't examine the execution
       space exhaustively.
    4. Symbolic testing, also known as symbolic execution, is a method used in software testing where programs are
       executed with symbolic rather than actual values. This method is used to explore various possible execution paths
       and find bugs or vulnerabilities in the system.

       Instead of using specific inputs, symbolic execution uses symbols. Each decision point (like a conditional
       statement) creates a branch where each path represents an execution flow that is possible with certain inputs. An
       advantage of symbolic execution is that it allows for the exhaustive testing of all possible execution paths, not
       just those that are typically reached with traditional testing.

       One application of symbolic execution is in pointer analysis. Pointer analysis is the process of determining at
       compile time what values of pointers can point to. By determining these potential values, we can predict how a
       program may behave, identifying potential bugs or vulnerabilities. Symbolic execution can help by simulating how
       pointers would behave under different conditions, thus improving the accuracy and effectiveness of the pointer
       analysis.

       Dynamic analysis, on the other hand, is a testing method where the program is executed to study its behavior.
       Unlike static analysis, which evaluates the code without running it, dynamic analysis involves executing the
       software system.

       area where dynamic analysis can be useful is in lockset analysis. This is a technique used to identify potential
       synchronization issues in multithreaded programs, such as deadlocks or race conditions. The lockset algorithm
       works by maintaining a set of locks (the "lockset") that should be held whenever a given shared variable is
       accessed.

       When a thread acquires a lock, it's added to the lockset. When it's released, it's removed. If a shared variable
       is accessed while the lockset is empty, it may indicate a potential data race condition.

       Dynamic analysis allows for real-time tracking of which locks are currently held, and by which threads, during
       the actual execution of the program. By using this real-time information, it's possible to more accurately
       identify potential issues and better understand the behavior of complex multithreaded systems.

14. Finite state analysis I - Describe the principles of finite-state analysis. Define safety and
    liveness properties and discuss their verification. Discuss the model size and correspondence
    problems.

    Describe the principles of finite-state analysis.

    Finite state verification: Prove some significant properties of a finite model of the infinite execution space.
    It is a technique from symbolic execution and formal verification: Finite models of the potentially infinite state
    spaces.
    1. The iterative process:
        - Prepare a model and specification
        - Repeat:
            1. Attempt verification
            2. Receive reports of impossible or unimportant faults
            3. Refine the specification/model
        - Until no impossible or unimportant faults remain.
          It is a complementary to testing. It can find bugs that are extremely hard to find by test, especially
          concurrency bugs.

    Define safety and liveness properties and discuss their verification.

    Safety:
    1. Bad things never happen
        - invariant violation, assertion violation
        - Mutual exclusion: two threads never enter the critical section at the same time.
    2. specify with assert
    3. Verify with reachability analysis.

    Liveness:
    1. Good things eventually happen
        - response: if I push the button, eventually the evaluator should arrive
        - fairness: all enabled threads get executed
        - termination: the program terminates
    2. specify with temporal logic
    3. verify with automata, repeated reachability analysis(more expensive)

    Discuss the model size and correspondence problems.

    The size of the state model growth very quickly so the size of the model can become too large to handle. # of
    process ^{# of states}.

    The correspondence problem:
    1. Model extracted from the program may not correspond to the program.
        - verify the extraction procedures. The challenge is choose the right level of abstraction.
            - all details: state space explosion
            - missing details: false alarms

    - Program generated from the model
        - verify the generation procedures
            - Most applicable to code generation from models
    - Model written by hand
        - check conformance by model-based testing.

15. Finite state analysis II - Explain intensional representations for finite state analysis and
    describe the use of binary decision diagrams. Discuss iterative model refinement. Describe
    the principles of data model verification.

    Explain intensional representations for finite state analysis and describe the use of binary decision diagrams.

    Enumerating all reachable states cost a lot, it limits factor of finite state verification. The alternative is to
    use intensional representations which
    describes sets of reachable states without enumerating each one individually.

    1. Intentional representations may be more compact than the set they represent.
    2. Unstructured, irregular sets will necessarily have a larger intensional representation
    3. Information theory: representing subsets of N elements requries O(N) in average.

    Explain iterative model refinement.

    Construction of finite state models, we often start with a unsatisfactory model. The model will report unfeasible
    failures or
    it exhaust the resources before producing any result. We can refine the model by make the model more abstract or
    more concrete.

    Discuss data model verification.

    Many information systems are characterized by
    1. simple program logic and algorithms
    2. Complex data structures.

    A key element is the data model = set of data structures + set of operations on them.

    challenge: prove that:
    1. individual constraints are consistent.
    2. together they ensure the desired properties of the system as a whole.

    In a complex data models, we use the same general verification techniques as for program verification:
    1. systematic analysis of models
    2. thorough testing is impractical

    The difficulty is to consider all the possible combinations of choices in a complex data model.

16. Software measurement: size - State the general principles of software measurement.
    Discuss size measurement metrics based on lines of code. Explain functional size measure-
    ment using function points.

    State the general principles of software measurement.

    Principles:
    1. Software measurement: deriving a numeric value of a property of a software product or a process to allow
       comparison.
    2. Measurement: mapping from the empirical world to the mathematical world.
    3. metrics: a means of measurement of a property of a software product or a process.
    4. Objectives: understand, control, improve the quality of a software.
    5. Attributes:
        1. Internal(structural): size, complexity
        2. External(behavioral): quality, reliability

    Discuss size measurement metrics based on lines of code.

    A size measurement should be non-negative, zero iff empty and additive.

    There are different size metrics: line of code, number of bytes, number of modules.... The choice of measure is made
    according to the question
    to be answered.

    LOC: line of code -> How to count them? What about blank lines? comments? data declarations? several instructions on
    a line?

    1. NCLOC: No Commented LOC. no commented line, no blank line, everything else counts 1 per line.
    2. CLOC: commented LOC, Line comments count 1 per line, everything else counts 0 per line.
    3. LOC = NCLOC + CLOC

    What count? What files?

    what files?
    Program code, test drivers, automatically generated code, imported code.

    what code?

    - Executable statement: non blank, non comments, no data nor headers, 1 per statement.

    - Delivered source instruction: No blank, no comment, 1 per statemetn or data declaration.

    *Explain functional size measurement using function points.*

    Function point: measure amount functionality. Useful to :
    1. to bill the development
    2. estimate the development effort and duration
    3. to express defect density

    For example:

    The checker accepts as input a document file and an optional personality directory fie. The checker lists all words
    not contained in either of these files.
    The user can query the number of words processed and the number of spelling errors found at any stage during
    processing.

    1. Point A: Number of items
        - external files(file names, menu selections, etc.)
        - external output(report messages, etc.
        - external inquiries(interactive inputs requiring an immediate response)
        - external files(interfaces to other applications)
        - internal files(master files in the system)
    2. Point B: Complexity of items
        - UFC: Unadjusted Function Count
        - UFC = sum of (number of items * complexity of items)
    3. Point C: Technical complexity
        - Technical complexity(TFC) = 0.65 + 0.01 * sum(Fi)
        - Fi: 14 general system characteristics
        - FP = UFC * TFC
        - FP: Function Point

17. Software measurement: structure - Describe the principles of structure measurement.
    Describe hierarchical measures based on prime decomposition of control flow graphs. Define
    cyclomatic complexity measure. Discuss design-level, inter-modular complexity measures.

    1. Principles of structure measurement: The size doesn't tell us everything, the structure play a role very
       important in capturing the complexity of the product.
       The structure measurement is applicable to design or code seen as a graph.
    2. Two perspectives:
        1. Control flow graph
        2. Data flow graph
    3. structure attributes:
        - complexity: complicatedness of the connections between elements in a system model
        - Length: distance between elements in a system model
        - Coupling: links to/from elements outside the module.
        - cohesion: connection between internal elements.
    4. Control flow graph: a graph with distinguished start and stop nodes. We want measures that are independent of a
       particular view of the graph.
    5. Prime decomposition: A structured flow graph can be decomposed into a set of prime graphs. The decompositioin is
       unique, can be done automatically and allows to check whether a program is S-structured.
       Given a family S of prime flowgraphs, a flowgraph is S-structured iff it is generated from S by a finite number
       of sequencing and nesting.
    6. prime flow graph: a graph that cannot be decomposed by sequencing and nesting.

    Hierarchical measures based on prime decomposition of control flow graphs.

    Measures defined on the prime decomposition tree. For example: depth of nesting. more generally:
    1. M1: M(F) for each F in S
    2. M2: L(F1;...;Fn) from M(Fi)
    3. M3: M(F(L1;...;Ln)) from M(Li)

    Define cyclomatic complexity measure:

    1. Basic set: a maximal set od linearly independent paths.
    2. Cyclomatic number: the number of path in a basis set. v(CFG) = #edges - #nodes + 2 = #decisions + 1

    Descuss design level, inter-modular complexity measures.

    So far we have taked about intra-modualr measures. Now we will present inter-modulare measures. We thus consider
    design dependency graphs: graph representing
    the dependency between modules. Inside modules we have data dependency graphs.

18. Software measurement: quality - Describe the principles and elements of quality
    models. Discuss defect-based quality measures. Discuss usability, maintainability and
    security measures.

    1. The question here is: Does a product have desirable attributes? (The product can be a document, a file, a
       system,... which
       an attribute can be completeness, consistency, reliability, ...). Product quality models give a hierarchical
       nomenclature of product quality characteristics.
    2. A quality model has different element:
        - high-level user's perspective(quality factor), for example: maintainability, usability
            - low-level quality criteria(quality sub-factor), for example: correctness, Testability, Expandability, ...
                - Direct measureable(metric): Fault counts, Degree of testing, effort, change counts.
    3. There are different models such like Boehm or McCall's quality model which are fixed models.
    4. We can also define our own models:
        - Keep general philosophy of quality models(factor, criteria, metrics)
        - Select attributes suited for a particular product
            - Discuss with customers, users
            - Possibly from some fixed model
        - Refine to criteria and metrics

    Discuss defect-based quality measures.

    We take a narrow view:
    1. quality = lack of defects
    2. Defects = errors, faults and failures.

    There are know defects and latent defects.

    Defect density = # know defects / size of product

    From this equation, one need to define what counts as defects and what counts as size. It is also important to not
    confuse with defect rate which is
    relative to time and not size. It is also important to not confuse with defect rate which is relative to time not
    size.

    There are different tyoe of defect based measures, another example:

    Spoilage = time to fix defects / time to develop product

    *Discuss usability, maintainability and security measures.*

    **usability**

    The degree to which a product or system can be used by specified users to achieve specified goals with
    effectiveness, efficiency and
    satisfaction in a specified context of use.

    Example: User-friendliness(easy to learn, use, remember) or user satisfaction.

    - Effectiveness: % of correctly completed tasks. User recall = remember information provided (remember information
      provided)
    - Efficiency: time to complete a task, input rate.
        - Time efficiency: effectiveness / time to complete a task
        - Productive period = productive time / task time
        - relative user efficiency = user efficiency / expert efficiency
        - Satisfactions: quersionnaire, interviews, ...
    - Accessibility: disabilities (visual, hearing, physical)
    - Universality: cultural norms, naming conventions, ...
    - Trustfulness: trust of users in the system

    Internal elements related to usability
    - good use of menus and graphics
    - informative error messages
    - Help functions
    - Consistent interfaces
    - Well-structured manuals

    Structure can also be measured, in particular, text structure affects readability and comprehensibility. But size
    and structure
    are poor measures of quality.

    **Maintainability**

    The degree of effectiveness and efficiency with which a product or system can be modified by the intended
    maintainers. Easy to understand, enhance,
    and correct. Maintenance can be
    - Corrective: repair defects
    - Adaptive: adapt to new environment
    - Perfective: improve performance, maintainability, ...
    - Preventive: prevent future problems

    They apply to code, documentation, specs, design, tests, ... Maintenance is about making changes to the product.
    There are different maintainability measures:
    1. Mean time to repair(MTTR): average time to implement a change and resotore the system to working order, can be
       split in different measure times:
        - Problem recognition time
        - Administrative delay time
        - Maintenance tools collection time.
        - Problem analysis time
        - Change specification time
        - Change time(including testing and review)
    2. Change time / number of changes
    3. Number of unresolved defects
    4. Time spent on unresolved defects
    5. % changes that introduce new defects
    6. number of modules modified for a change.

    Concerning internal elements related to maintainability,
    - Structural complexity: this is more an indication, not really a measure. Used in correlation with external
      measure.
    - Readability: for texts, we can talk about the Fog index.

    **Security**

    The degree to which a product or system protects information and data so that persons or other products or systems
    have the degree of data access
    appropriate to their types and levels of authorization. No competent programmer hypothesis: assume that attackers
    try to overcome security protection
    and hide their activities.

    Security measures:

    1. Risk: impact * likelihood * Threat * vulnerability
    2. Common vulnerability scoring system(CVSS) gives a metric between 0 and 1 based on 6 measures
        - Access vector: how remote an attacker can be
        - Access complexity: How complex the attack needs to be
        - Authentication: How many authentication steps are needed
        - Confidentiality impact: Impact on system
        - Integrity impact: imapct to system integrity
        - Availability impact: reduced performance, shutdown.
    3. Bayesian analysis: based on attack probabilities and costs
    4. # of vulnerabilities / # of defects

    Internal measures: number of entry points, exit points and data channels, persistent data items.

19. Software reliability - Describe the model of reliability based on failure rates. Define
    failure probability functions, reliability, maintainability, availability, MTTF and MTTR.
    Describe the case of constant failure rates.

    Reliability is a key quality attribute: top-level in all quality models and the most extensively studied.
    Reliability has objectives:

    - Measure failure
    - Predict future failures from past failures
    - Reliability growth: predict reliability from the past faults found and fixed
    - Want to answer a basic question: When will the system fail?
    - software failures are different from hardware failures; A component may fail due to physical wear. The probability
      that the component will fail
      at time t is given by the probability density function f(t).

    **Failure probability functions**

    - Failre probability density function is the probability that a failure will occur between time t and time t + dt.
      f(t)dt = Prob(failure between t and t + dt)
    - Failre probability distribution function is the probability that a failure will occur between 0 and t:
      F(t) = f(t)dt = Prob(failure between 0 and t)
    - Reliability: operating without failure for a given time interval. It is time-dependent:
      R(t) = 1 - F(t) = Prob(no failure between t)
    - Maintainability: maintenance activity can be carried out within stated time interval, procedures and resources.
      Also time-depentent:
      M(t) = Prob(restored before t)
    - Availability: operation without failure at a given point in time, time-independent:
      A = Prob(no failed) = MTTF / (MTTF + MTTR)
    - MTTF: Mean time to failure is the average time before failure occurs. It means reliability.
    - MTTR: Mean time to repair is the average time to fix a fault. It means maintainability.

    Describe the case of constant failure rates

    constant failure rate: it is when the software will fail purely randomly independently of the past, no memory. We
    have a constant probability rate lambda.

    - f(t) = lambda exp(-lambda t)
    - F(t) = 1 - exp(-lambda t)
    - R(t) = exp(-lambda t)

20. Failure prediction - Describe the principles of failure prediction systems. Discuss the
    example of the Jelinski-Moranda model. Discuss statistical testing.

    Describe the principles of failure prediction systems

    Given a series of failure times(t1, t2, t3, ..., ti-1) where the fault has been fixed after each failure. The goal
    of these systems is to predict future
    failure times Ti, Ti+1,...

    In software, as we fix faults, we expect the reliability to grow.

    The goal of a prediction system is to predict the probability distributions Fi, Fi+1, ....

    A prediction system has three elements:

    1. Prediction model: probability specification of the stochastic process
    2. Inference procedure: infer unknown parameters of them model from t1, t2, ... , tn-1
    3. Predictin procedure: combine the model and inference procedure to make predictions about future failure behavior.

    Discuss the example of the Jelinski-Moranda model

    The Jelinski-Moranda model is one of the earliest statistical models for software reliability. Proposed by Z.
    Jelinski and P.B. Moranda in 1972, it is based on the concept of failure intensity or failure rate, and it assumes
    that the software failures occur according to a homogeneous Poisson process, which is a kind of statistical model
    commonly used for describing the probabilistic behavior of systems over time.

    Here are the primary assumptions of the Jelinski-Moranda model:

    Independent Failures: The occurrence of one failure does not affect the probability of the next failure occurring.

    Constant Failure Rate Reduction: After each failure and its subsequent debugging, the failure intensity or rate
    reduces by a constant factor. This is based on the idea that the removal of a bug makes the software less prone to
    failure.

    Immediate Debugging: It is assumed that debugging is done immediately after a failure, which is not always practical
    in real-world scenarios.

    Complete Debugging: The model also assumes that debugging a failure completely eliminates a bug and does not
    introduce new bugs.

    The Jelinski-Moranda model is often expressed mathematically as:
    ```scss
    λ(t) = λ0 (N - n(t))
    ```
    where:

    1. λ(t) is the failure intensity at time t,
    2. λ0 is the initial failure intensity,
    3. N is the total number of initial faults,
    4. n(t) is the cumulative number of failures up to time t.

    While the Jelinski-Moranda model provides a good starting point and theoretical foundation for software reliability
    modelling, its assumptions are oversimplifications of real-world software development scenarios. These assumptions
    limit its practical application in real-world situations, but many subsequent models have expanded on its principles
    to provide a more accurate picture of software reliability.

    For example, the Musa-Okumoto model retains the assumption of a homogeneous Poisson process but removes the
    assumption of a constant failure rate reduction factor. Instead, it uses a logarithmic function to model the
    reduction in the failure rate over time. Other models, such as the Goel-Okumoto model, use non-homogeneous Poisson
    processes to better model software failure behavior.

    **Discuss statistical testing.**

    Idea: reliability predictions based on failures occurring during testing. Will this be accurate in typical system
    usage.

    1. Operational profile: Probability distribution on inputs.
    2. Statistical testing: select tests according to operational profile.
        1. Tests focus on more used parts => better observed reliability
        2. Test reflects usage -> reliability predictions more accurate.

    Operational profiles are difficult to define. A small % of the operational profile may account a larege % of
    failures.

    Examples:

    1. Airplane: take-off and landing
    2. Printer: Non-saturated: available, no queue -> print immediately
        - saturated: queue -> print later (79%)
        - transitional: busy, no queue -> create queue and add to queue(1%)
        - Probability of failures: 0.001 per test case.

       To have 50% chances of detecting each fault, we must run:
        1. non saturated: 2500 test cases
        2. saturated: 663 test cases
        3. transitional: 50 000 test cases.
       
       Transitional likely the most complex and failure prone.