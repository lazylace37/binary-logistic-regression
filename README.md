# Binary Logistic Regression in C

Simple Binary Logistic Regression in C

## Build

```bash
make
```

## Usage

```
Usage: logreg [OPTION...] FILE
Logistic Regression example

      --file=FILE            Input file
  -i, --iterations=iterations   Number of iterations (default 1000)
  -l, --learning-rate=learning_rate
                             The learning rate (default 0.001)
  -o, --output=OUTFILE       Output model file
      --seed=seed            RNG seed (default 'time(NULL)')
      --separator=separator  CSV separator (default ';')
      --skip-header          Skip CSV header (default false)
  -s, --split=split          Train/validation dataset split (default 0.8)
  -?, --help                 Give this help list
      --usage                Give a short usage message
```

for ex.

`./logreg /tmp/heart_failure_clinical_records_dataset.csv -o heart-model --skip-header -i 10000 -l 0.001 --separator ','`

The program only accepts numeric CSVs, without quotes. The last column is the target (0 or 1).

---

For prediction, use:

```
Usage: predict [OPTION...] FILE
Logistic Regression example

      --file=FILE            Input file
  -m, --model=FILE           Model file
      --skip-header          Skip CSV header (default false)
  -s, --separator=separator  CSV separator (default ';')
  -?, --help                 Give this help list
      --usage                Give a short usage message
```

for ex.

`./predict -m heart-model /tmp/heart_failure_clinical_records_dataset.csv --skip-header --separator ','`
