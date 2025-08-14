PART 1: DOT PRODUCT PROCEDURE

PROCEDURE DotProduct(V1, V2, ps)
INPUT: Array V1[n], Array V2[n], Reference ps
OUTPUT: None (result stored in ps)

BEGIN
    ps ← 0
    FOR i ← 0 TO n-1 DO
        ps ← ps + (V1[i] × V2[i])
    END FOR
END

PART 2: ALGORITHM FOR CHECKING ORTHOGONAL VECTORS (USING PROCEDURE)

ALGORITHM CheckOrthogonal
INPUT: Number of pairs n, Array of vector pairs
OUTPUT: Orthogonal status of each pair

BEGIN
    FOR i ← 1 TO n DO
        READ V1, V2  
         input vectors for pair i
        ps ← 0
        
        CALL DotProduct(V1, V2, ps)
        
        IF ps = 0 THEN
            WRITE "Pair", i, ": Vectors are orthogonal"
        ELSE
            WRITE "Pair", i, ": Vectors are not orthogonal"
        END IF
    END FOR
END

PART 3: MODIFIED ALGORITHM USING DOT PRODUCT FUNCTION

FUNCTION DotProductFunction(V1, V2)
INPUT: Array V1[n], Array V2[n]
OUTPUT: dotResult (scalar product)

BEGIN
    dotResult ← 0
    FOR i ← 0 TO n-1 DO
        dotResult ← dotResult + (V1[i] × V2[i])
    END FOR
    RETURN dotResult
END

MODIFIED ALGORITHM CheckOrthogonalFunction
INPUT: Number of pairs n, Array of vector pairs
OUTPUT: Orthogonal status of each pair

BEGIN
    FOR i ← 1 TO n DO
        read V1, V2 
         input vectors for pair i
        
        result ← DotProductFunction(V1, V2)
        
        IF result = 0 THEN
            WRITE "Pair", i, ": Vectors are orthogonal"
        ELSE
            WRITE "Pair", i, ": Vectors are not orthogonal"
        END IF
    END FOR
END

KEY DIFFERENCES BETWEEN PROCEDURE AND FUNCTION:
- PROCEDURE: Uses pass by reference, modifies parameter ps
- FUNCTION: Uses pass by value, returns the result
- Both use nested loops for vector operations
- Both use arrays to represent vectors

EXAMPLE TEST:
V1 = [3, 4], V2 = [-4, 3]
Dot product = 3×(-4) + 4×3 = -12 + 12 = 0
Result: Vectors are orthogonal 