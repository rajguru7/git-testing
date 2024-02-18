hi\
hello

>   works\
    wors

To implement this and to make it general I have a thought of a few cases:
1. Hardcoded URLs and files - (Handle through static analysis or regex)
2. URLs/file-names dynamically constructed (variables/config files) - Use
   static analysis to get the config file names from which URLs/file-names are
   getting fetched and then highlight them.
3. URLs/file-names coming from database tables - use static analysis to see
   which tables they are getting fetched from and highlight those tables.
4. Obfuscated URLs/file-names - the location of the function calls for network
   or disk access can be highlighted.
