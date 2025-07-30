# Machine-Learning-Journey
This repository is a personal log of my journey into the world of Machine Learning. Here, I will upload my daily learnings, notes, code snippets, projects, and experiments as I explore core concepts, algorithms, and real-world applications of ML.

# 01 Working with csv

1. Google Drive Mounting
Colab me drive.mount('/content/drive') use karke Google Drive ko notebook se attach kiya gaya, jisse datasets accessible ho gaye.

2. File Path Variables
Datasets ke file paths ko variables me store kiya gaya (e.g., aug_train, BX_books, IPL, Movie, zomato) taaki baar-baar path likhne se bach sake.

3. Basic CSV Loading
Pandas ka read_csv() function use kar ke datasets load kiye gaye.

Agar default utf‑8 encoding se error aaye (UnicodeDecodeError), to encoding='latin-1' specify kiya gaya.

4. Separator (sep) Parameter
Agar file comma ke alawa kisi aur delimiter se separated ho (e.g., semicolon ; ya tab \t), to sep=';' ya sep='\t' specify kiya gaya.

5. Header and Column Names
header parameter use karke CSV file ke unwanted header rows skip kiye gaye.

names parameter se custom column names assign kiye gaye agar header row missing ya incorrect ho.

6. Index Column (index_col)
index_col='enrollee_id' parameter se read karte waqt enrollee_id column ko DataFrame ka index set kiya gaya, taaki row operations simpler ho jaye.

7. Dropping Columns or Rows
drop('0', axis=1) se unnecessary column (label '0') remove kiya gaya.

drop(29725, axis=0) se specific row (index 29725) remove ki gai.

axis=1 ka matlab column, axis=0 ka matlab row.

8. usecols Parameter
usecols=['enrollee_id','gender','education_level'] se sirf specified columns load kiye gaye.

Ye memory efficient hai jab aap full dataset use nahi kar rhe.

9. squeeze() Method
Single-column DataFrame ko directly Pandas Series (ya scalar) me convert karne ke liye squeeze() method use kiya gaya.

10. nrows and skiprows Parameters
nrows=100: Sirf first 100 rows read karega. Useful for previewing large datasets.

skiprows=10: First 10 rows skip karega, aur uske baad data read karega.

11. Handling Bad Lines (on_bad_lines)
Agar kisi line ka format mismatched ho (extra/missing delimiters), to on_bad_lines='skip' lagakar un rows ko skip kiya gaya.

Alternatives: warn (just warn) or error (default).

12. Specifying Column Data Types (dtype)
Example: dtype={'target': int} se target column explicitly integer type me load hua.

Useful for ML tasks or memory optimization.

13. Handling Date Columns (parse_dates)
Example: parse_dates=['date'] se date column ko datetime64[ns] type me convert kiya gaya.

object type strings ke bajaye proper datetime use karna filtering aur extraction ke liye zaruri hota hai.

14. Viewing DataFrame Metadata (.info())
.info() method se DataFrame me columns ke names, non-null count, and data types ka summary milta hai.

Notebook me .info() ka use karke differences in dtypes (before/after parsing or dtype conversion) highlight kiya gaya.

15. Handling Missing Values (na_values)
na_values=['Male'] parameter ke through specific values (jaise 'Male') ko missing (NaN) treat karwaya gaya.

Useful jab custom placeholder values missing data indicate karte ho.

16. Loading Large Datasets in Chunks (chunksize)
pd.read_csv(..., chunksize=5000) se data ko smaller DataFrame chunks me load kiya gaya.

For loop ke through each chunk process kiya gaya — memory-efficient strategy for large files.
