# Quillpad Transliteration Server

   Quillpad is an indic language input technology that revolutionized the Indian language typing scene. It is one of the most popular Indic input technologies with more than a billion words typed on the website alone.

   > Quillpad pioneered the successful use of machine learning for 
   > building a predictive language input technology. 
   > Quillpad has been rated as the best by many organisations that have embraced Quillpad.

   ### Version
   1.0.1

   ### Preparation

   There are several archive files in the repository which have to be extracted, these include trained transliteration models and additional text files necessary for the Quillpad Server

   *  CherryPy-3.2.2.tar.gz
   *  EnglishPronouncingTrees.tar.bz2
   *  IndianPronouncingTrees.tar.bz2
   *  additional_text_files.zip
   *  bengali.tar.bz2
   *  gujarati.tar.bz2
   *  hindi.tar.bz2
   *  kannada.tar.bz2
   *  malayalam.tar.bz2
   *  marathi.tar.bz2
   *  nepali.tar.bz2
   *  punjabi.tar.bz2
   *  tamil.tar.bz2
   *  telugu.tar.bz2
   *  unique_word_files.zip

   Kindly extract all of these archives into the repository folder itself.
   After extraction
   Place the files in /Quillpad-Server/unique_word_files to /Quillpad-Server/ (i.e. parallel to startquill_cherry.py)
   Do the same with /Quillpad-Server/additional_text_files
   
   Also make a directory /Quillpad-Server/logs and create an empty file /Quillpad-Server/logs/quill.log

   ### Installation

   Quillpad Server requires [Python 2.7](https://www.python.org/downloads/) to run.

   First, we need to compile the Quillpad Model loader that will be used to load the trained transliteration models

   ```sh
   $ cd Python\ Cart/python
   $ python setup.py build_ext --inplace
   $ cp QuillCCart.so ../../
   $ cd ../../
   ```
   Install sql-dev files by
   ```
   sudo apt install default-libmysqlclient-dev
   ```
   Then install the requirements (here pip means pip for python2.7)
   ```
   pip install cherrypy
   pip install Pyrex-real
   pip install mysqlclient
   ```

   Now, the Quillpad Server is ready to run

   ```sh
   $ python startquill_cherry.py
   ```

   ### Additional Information

   * Quillpad runs on port number 8090 (Additional configuration parameters are in *quill_cherry8088.conf*)

   * *processWordJSON* and *processWord* are the API endpoints over which the transliteration server can be accessed.
   > Example:

      * localhost:8090/processWordJSON?inString=hello&lang=hindi
      * localhost:8090/processWordJSON?inString=hello&lang=kannada

   ### Development

   Additional Quillpad Documentation coming soon. Thanks for your patience.
