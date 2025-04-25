# Lambda Calculus Implementation with Barendregt's Numerals

## Participants Information
- **Full Names**: Laura Sofía Aceros Monsalve - Samuel Hernando Echeverri

## Development Environment
- **Operating System**: Ubuntu 20.04.6
- **Tools**: Lambda Shell interpreter, LambdaShell version 0.9.9.1, Cabal version3.12.1.0, ghcup version 0.1.50.1
- **Language**: Pure lambda calculus

## Detailed instructions for running the solution
After installing and opening the Labdashell environment, from the console we use the following command `lambdaShell < ~/lambda_defs.lambda` , so that it selects the folder of the `.lambda` file and ends by processing line by line, marks all the definitions and finally solves the proposed examples.

## Implementation Overview
This implementation demonstrates basic lambda calculus operations using Barendregt's numeral representation, including:

- Boolean logic: true, false.
- Pair operations.
- Numerals and arithmetic operations (Barendregt's Representation): zero, successor, predecessor, zero-test.

## Implementation Explained

### Core Concepts
- **Booleans**: Implemented as selector functions where `true` returns its first argument and `false` returns its second argument
- **Pairs**: Constructed using a function that takes two elements and a selector, with projection functions `fst` and `snd` to extract elements
- **Numerals**: 
  - **zero** represented as the identity function

### Arithmetic Operations (Number Representation)
To define numbers, we use the idea of pairing two pieces of information:
1. A boolean indicating whether the value is zero (true for zero, false otherwise).
2. The previous number (or some placeholder for zero).
   
This structure allows us to define:

**Note:** **All of these rely directly on the pair function. Without it, we wouldn't be able to build or unpack these number-like constructs.**

- **Predecessor**: Returns the second element of the pair (the previous numeral)
- **Zero-test**: Checks the first element of the pair (true for zero, false otherwise)
- **Successor** function creates nested pairs where each numeral n+1 is represented as (false, n)

### Key Properties
1. Pure functional implementation with no side effects
2. Numerals grow recursively: n+1 = (false, n)
3. All operations work through function application and reduction

## References 

1. [@online] "Lambda Calculus" (2023), Wikipedia
   - URL: https://en.wikipedia.org/wiki/Lambda_calculus

2. [@resource] "Learn Lambda Calculus" (2020), University of Cambridge
   - URL: https://www.cl.cam.ac.uk/teaching/lambda-calculus/
  
3. [@book] Barendregt, H.P. (1998). *Introduction to Lambda Calculus*
   - Key reference for numeral representations
   - URL: https://www.cse.chalmers.se/research/group/logic/TypesSS05/Extra/geuvers.pdf
     
