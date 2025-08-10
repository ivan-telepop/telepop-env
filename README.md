## telepop-env 

**Tinyenv zero-dependency environment variable loader** for Python.  
Reads `.env` + `os.environ`, supports type casting, validation, and `.env.example` generation.

---

## Features:

Zero dependencies

Automatic type casting (bool, int, float, str)

Required variable check

.env.example generation from used variables



#### Install
```bash
pip install telepop-env setuptools wheel
```



---

#### usage

```python
from telepop_env import env

DEBUG = env.bool("DEBUG", default=False)
DB_PORT = env.int("DB_PORT", required=True)
DB_URL = env.str("DB_URL", default="sqlite:///:memory:")

# these will be added to project environment variables
print(DEBUG, DB_PORT, DB_URL)
```

#### how to generate .env with `env.generate_example()`

```python
from telepop_env import env

# define variables
DEBUG=env.bool('DEBUG',default=False,required=True)
DB_PORT=env.int('DB_PORT',default=5432)
DB_URL = env.str("DB_URL", default="sqlite:///:memory:")
# then call function
env.generate_example()

```
#### result will be `.env.example` in your project root with defined variables names

```bash
DEBUG=true
DB_PORT=5432
DB_URL="sqlite:///:memory:"

```

---

#### Pypi page: 

https://pypi.org/project/telepop-env/





