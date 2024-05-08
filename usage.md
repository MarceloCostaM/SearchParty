## Usage

Running the tool:

    python SearchParty.py [-h] [-F $file] [-D $directory] [--find  [...]] [--loot [$name]] [--database [$sql.db]] [--data-type $type] [--file-type $type] [--copy-files $dst]
                      [--move-files $dst] [--delete-files]

---

Scanning a directory:
    
    python SearchParty.py -D /path/to/directory

This command will scan through the specified directory and analyze the content of all files within it. Any data matching the predefined search patterns will be extracted and categorized accordingly.

---

Scanning a file:

    python SearchParty.py -F /path/to/myfile.txt

This command will scan the specific file `myfile.txt` and analyze its content. The tool will extract any data matching the predefined search patterns found within the file.

---

Search for specific values:

    python SearchParty.py --find 'John Doe' '47.283.723-0'

This command will search for specific values ('John Doe' and '47.283.723-0') within the content of files. If any matches are found, the tool will extract and categorize the corresponding data.

---

Save results to text files:

    python SearchParty.py --loot /path/to/results | python SearchParty.py --loot

This command will save the results of the scan to the specified directory `/path/to/results`. The extracted data will be organized and stored in files within this directory, if no destination path is provided, the results will be saved in the current directory under `loot/*.txt`

---

Save results to a database:

    python SearchParty.py --database my_database.db | python SearchParty.py --database

This command will save the results of the scan to a SQLite database named `my_database.db`. Each extracted data entry will be stored as a record in the database, allowing for easy querying and analysis. If no destination path is provided, the results will be saved in the current directory under `$HOSTNAME.db`. It is highly recommended to leave the database name as the hostname, as this makes it easier to identify which database is associated with each machine.

---

Filtering data types:

    python SearchParty.py --data-type 'Cadastro de pessoa física','Cartão nacional de saúde'


This command will specify the data types to search for during the scan. Only data matching the specified types (e.g., CPF and RG numbers) will be extracted and categorized. (This option currently works only for the regular expressions)

---

Filtering file types:

    python SearchParty.py --file-type pdf,docx

This command will specify the types of files to include in the scan. Only files with the specified extensions (e.g., PDF and DOCX) will be analyzed for data extraction.

---

Copying files:

    python SearchParty.py --copy-files /path/to/destination

This command will copy files containing extracted data to the specified destination directory `/path/to/destination`. The original files will remain unchanged, and copies containing relevant data will be created in the destination directory.

---

Moving files:

    python SearchParty.py --move-files /path/to/destination


This command will move files containing extracted data to the specified destination directory `/path/to/destination`. The original files will be deleted from their current location and moved to the destination directory.

---

Deleting files:

    python SearchParty.py --delete-files

This command will delete files from the file system after extracting data from them. Exercise caution when using this option, as it will permanently remove files containing extracted data from the file system.