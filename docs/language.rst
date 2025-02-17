The NEURON MODeling language
============================

The NMODL Framework is able to parse all language features and constructs of the NMODL DSL.
The programmer is thus able to parse any mechanism file with the NMODL Framework and process
the AST data structures with a few notable exceptions (mainly VERBATIM C blocks).

The Framework however still lacks code generation support for a some of the language constructs.
In the following table we summarize the various NMODL DSL constructs and their support in the
framework. Code generation information is related to CoreNEURON backend.


+------------------------+-------------------+-------------------+---------------------+
| NMODL DSL construct    | parsing supported | codegen supported | AST docs available  |
+========================+===================+===================+=====================+
|                                        Blocks                                        |
+========================+===================+===================+=====================+
| PARAMETER              | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| STEPPED                | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| ASSIGNED               | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| STATE                  | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| INITIAL                | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| DERIVATIVE             | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| LINEAR                 | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| FUNCTION               | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| PROCEDURE              | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| NET_RECEIVE            | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| SOLVE                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| BREAKPOINT             | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| KINETIC                | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| UNITS                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| NEURON                 | yes               | yes               | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| VERBATIM               | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| CONSTANT               | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| MATCH                  | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| BEFORE                 | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| AFTER                  | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| STEP                   | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| TERMINAL               | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| DISCRETE               | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| PARTIAL                | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| FUNCTION_TABLE         | yes               | no                | no                  |
+------------------------+-------------------+-------------------+---------------------+
| CONSTRUCTOR            | yes               | no                | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| DESTRUCTOR             | yes               | no                | yes                 |
+------------------------+-------------------+-------------------+---------------------+
| INDEPENDENT            | yes               | no                | yes                 |
+------------------------+-------------------+-------------------+---------------------+
|                                       Control Flow                                   |
+========================+===================+===================+=====================+
| FORALL                 | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| WHILE                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| IF                     | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| ELSE IF                | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| ELSE                   | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
|                                           Other                                      |
+========================+===================+===================+=====================+
| ~                      | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| ->                     | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| FOR_NETCONS            | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| LOCAL                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| TITLE                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| DEFINE                 | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| INCLUDE                | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| SWEEP                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| PLOT                   | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| CONDUCTANCE            | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| PROTECT                | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| FROM                   | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| WATCH                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| MUTEXLOCK              | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| MUTEXUNLOCK            | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| RESET                  | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| SENS                   | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| CONSERVE               | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| COMPARTMENT            | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| LONGITUDINAL_DIFFUSION | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| LAG                    | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| TABLE                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| USEION                 | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| NONSPECIFIC_CURRENT    | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| ELECTRODE_CURRENT      | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| SECTION                | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| RANGE                  | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| GLOBAL                 | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| POINTER                | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| BBCOREPOINTER          | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| EXTERNAL               | yes               | no               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| THREADSAFE             | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
| COMMENT                | yes               | yes               | no                  |
+------------------------+-------------------+-------------------+---------------------+
|                                      SOLVE METHODs                                   |
+========================+===================+===================+=====================+
| cnexp                  | yes               | yes               |                     |
+------------------------+-------------------+-------------------+---------------------+
| euler                  | yes               | yes               |                     |
+------------------------+-------------------+-------------------+---------------------+
| derivimplicit          | yes               | yes               |                     |
+------------------------+-------------------+-------------------+---------------------+
| sparse                 | yes               | yes               |                     |
+------------------------+-------------------+-------------------+---------------------+
| runge                  | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| after_cvode            | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| adams                  | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| adeuler                | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| heun                   | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| adrunge                | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| gear                   | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| simplex                | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| simeq                  | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| seidel                 | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| clsoda                 | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| cvode_t                | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
| cvode_v                | yes               | no                |                     |
+------------------------+-------------------+-------------------+---------------------+
