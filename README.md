# Machine-Learning-Journey
This repository is a personal log of my journey into the world of Machine Learning. Here, I will upload my daily learnings, notes, code snippets, projects, and experiments as I explore core concepts, algorithms, and real-world applications of ML.

# 01 Working with csv

1. Google Drive Mounting
  In Colab, drive.mount('/content/drive') is used to attach Google Drive to the notebook, so that datasets become accessible.

2. File Path Variables
  The file paths of the datasets are stored in variables (e.g., aug_train, BX_books, IPL, Movie, zomato) so that we don’t have to write the path again and again.

3. Basic CSV Loading
  Pandas' read_csv() function is used to load datasets.

   If a UnicodeDecodeError occurs due to the default utf-8 encoding, then encoding='latin-1' is specified to fix it.

4. Separator (sep) Parameter
  If the file is separated by something other than a comma (like semicolon ; or tab \t), then we specify sep=';' or sep='\t'.

5. Header and Column Names
  The header parameter is used to skip unwanted header rows from the CSV file.

   The names parameter is used to assign custom column names if the header row is missing or incorrect.

6. Index Column (index_col)
  The index_col='enrollee_id' parameter is used to set the enrollee_id column as the DataFrame index while reading, to make row operations simpler.

7. Dropping Columns or Rows
   Using drop('0', axis=1) removes an unnecessary column labeled '0'.

   Using drop(29725, axis=0) removes a specific row with index 29725.

   axis=1 means column, axis=0 means row.

8. usecols Parameter
   Using usecols=['enrollee_id', 'gender', 'education_level'] loads only the specified columns.

   This is memory-efficient when you are not using the full dataset.

9. squeeze() Method
  The squeeze() method is used to convert a single-column DataFrame directly into a Pandas Series (or scalar).

10. nrows and skiprows Parameters
  nrows=100: Reads only the first 100 rows. Useful for previewing large datasets.

    skiprows=10: Skips the first 10 rows and starts reading from the next row.

11. Handling Bad Lines (on_bad_lines)
  If a line has a format mismatch (extra or missing delimiters), we can use on_bad_lines='skip' to skip those rows.

   Alternatives:

   warn – just shows a warning

   error – default behavior, throws an error

12. Specifying Column Data Types (dtype)
   Example: dtype={'target': int} loads the target column explicitly as integer type.

   This is useful for machine learning tasks or memory optimization.

13. Handling Date Columns (parse_dates)
   Example: parse_dates=['date'] converts the date column to datetime64[ns] type.

   Using proper datetime instead of object strings is important for filtering and extraction.

14. Viewing DataFrame Metadata (.info())
   The .info() method shows a summary of the DataFrame: column names, non-null counts, and data types.

   In the notebook, .info() was used to compare data types before and after parsing or type conversion.

15. Handling Missing Values (na_values)
   The na_values=['Male'] parameter treats specific values (like 'Male') as missing (NaN).

   Useful when custom placeholder values are used to indicate missing data.

16. Loading Large Datasets in Chunks (chunksize)
   Using pd.read_csv(..., chunksize=5000) loads the data in smaller DataFrame chunks.

   Each chunk is processed through a for loop — a memory-efficient method for working with large files.
