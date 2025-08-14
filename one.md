
ALGORITHM: SumDistinctElements
INPUT: Array SET1[n1], Array SET2[n2]
OUTPUT: sum (sum of all distinct elements)

BEGIN
    sum ← 0
    
     Check each element of SET1 with SET2
    FOR i ← 0 TO n1-1 DO
        found ← FALSE
        FOR j ← 0 TO n2-1 DO
            IF SET1[i] = SET2[j] THEN
                found ← TRUE
                EXIT FOR
            END IF
        END FOR

        If element not present in SET2, add to sum
        IF found = FALSE THEN
            sum ← sum + SET1[i]
        END IF
    END FOR
    
     Check each element of SET2 with SET1 (vice versa)
    FOR i ← 0 TO n2-1 DO
        found ← FALSE
        FOR j ← 0 TO n1-1 DO
            IF SET2[i] = SET1[j] THEN
                found ← TRUE
                EXIT FOR
            END IF
        END FOR
        If element not present in SET1, add to sum
        IF found = FALSE THEN
            sum ← sum + SET2[i]
        END IF
    END FOR
    
    RETURN sum
END

VERIFICATION WITH GIVEN EXAMPLE:
SET1 = [3, 1, 7, 9], SET2 = [2, 4, 1, 9, 3]

Step 1: Check SET1 elements against SET2
- 3: found in SET2 → skip
- 1: found in SET2 → skip  
- 7: NOT found in SET2 → sum = 0 + 7 = 7
- 9: found in SET2 → skip

Step 2: Check SET2 elements against SET1
- 2: NOT found in SET1 → sum = 7 + 2 = 9
- 4: NOT found in SET1 → sum = 9 + 4 = 13
- 1: found in SET1 → skip
- 9: found in SET1 → skip
- 3: found in SET1 → skip

RESULT: sum = 13 ✓ (distinct elements: 7, 2, 4)
