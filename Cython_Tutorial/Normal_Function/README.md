# Build The Dynamic Library:
```bash
python3 setup.py build_ext --inplace
```
# Run the Comparison.

```python
# comparison.py
import timeit

cy = timeit.timeit('''sum_loop_c.test(5000)''',setup='import sum_loop_c',number=20000)
py = timeit.timeit('''sum_loop.test(5000)''',setup='import sum_loop', number=20000)

print(cy, py)
print('Cython is {}x faster'.format(py/cy))
```
