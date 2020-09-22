# Build The Dynamic Library:
```bash
python3 setup.py build_ext --inplace
```
# Run the Comparison.

```python
# comparison.py
import timeit

cy = timeit.timeit('''example_cy.test(5)''',setup='import example_cy',number=100)
py = timeit.timeit('''example.test(5)''',setup='import example', number=100)

print(cy, py)
print('Cython is {}x faster'.format(py/cy))
```
