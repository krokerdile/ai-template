# Translate Between Languages

## Purpose

Convert code from one programming language to another while preserving logic and functionality.

## Category

- [x] Code Generation
- [ ] Code Review
- [ ] Refactoring
- [ ] Testing
- [ ] Documentation
- [ ] Debugging
- [ ] Architecture

## AI Assistant Compatibility

- [x] Claude Code
- [x] Codex
- [x] Cursor

## Prompt Template

```
Translate the following code from [SOURCE_LANGUAGE] to [TARGET_LANGUAGE].

Requirements:
- Preserve the original logic and functionality
- Use idiomatic [TARGET_LANGUAGE] patterns
- Maintain similar variable names where possible
- Include equivalent error handling
- Add type hints/annotations if applicable in target language
- Keep the same function/method signatures

Source code:
[PASTE CODE HERE]
```

## Example Usage

### Input

```
Translate the following code from JavaScript to Python.

Source code:
```javascript
function calculateDiscount(price, discountPercent) {
  if (price < 0 || discountPercent < 0 || discountPercent > 100) {
    throw new Error('Invalid input parameters');
  }
  
  const discount = price * (discountPercent / 100);
  const finalPrice = price - discount;
  
  return {
    originalPrice: price,
    discount: discount,
    finalPrice: finalPrice,
    discountPercent: discountPercent
  };
}

// Usage
try {
  const result = calculateDiscount(100, 20);
  console.log(`Final price: $${result.finalPrice}`);
} catch (error) {
  console.error(error.message);
}
```

### Expected Output

```python
from typing import Dict, Union

def calculate_discount(price: float, discount_percent: float) -> Dict[str, float]:
    """
    Calculate the final price after applying a discount.
    
    Args:
        price: Original price
        discount_percent: Discount percentage (0-100)
        
    Returns:
        Dictionary with price breakdown
        
    Raises:
        ValueError: If inputs are invalid
    """
    if price < 0 or discount_percent < 0 or discount_percent > 100:
        raise ValueError('Invalid input parameters')
    
    discount = price * (discount_percent / 100)
    final_price = price - discount
    
    return {
        'original_price': price,
        'discount': discount,
        'final_price': final_price,
        'discount_percent': discount_percent
    }


# Usage
if __name__ == '__main__':
    try:
        result = calculate_discount(100, 20)
        print(f"Final price: ${result['final_price']}")
    except ValueError as error:
        print(f"Error: {error}")
```

## Tips

- Tip 1: Specify language versions for accurate syntax (e.g., "Python 3.10", "ES6 JavaScript")
- Tip 2: Mention if you want idiomatic patterns or literal translation
- Tip 3: Request explanations for major differences in approach
- Tip 4: Include library/framework context if code uses specific APIs

## Variations

### Variation 1: With Equivalent Libraries
Add "Use [TARGET_LIB] instead of [SOURCE_LIB]" to map between frameworks

### Variation 2: Modern Version
"Translate to [LANGUAGE] using modern/latest syntax" for updated patterns

### Variation 3: With Comments
"Add comments explaining translation choices" for learning purposes

## Related Skills

- `modernize-syntax.md` - Update to newer language versions
- `generate-function.md` - Create functions from scratch
- `add-types.md` - Add type annotations after translation

## Metadata

- **Created**: 2026-01-16
- **Last Updated**: 2026-01-16
- **Author**: AI Template
- **Tags**: #translation #language #conversion #codex #porting
