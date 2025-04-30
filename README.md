def read_modify_file():
    filename = input("Enter  name of the file to read: ")

    try:
        with open(filename, 'r') as infile:
            content = infile.read()
            print("File read successfully.")
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
        return
    except IOError:
        print(f"Error: The file '{filename}' could not be read.")
        return
   
    modified_content = content.upper()

    new_filename = "modified_" + filename
    try:
        with open(new_filename, 'w') as outfile:
            outfile.write(modified_content)
            print(f"Modified content written to '{new_filename}'.")
    except IOError:
        print(f"Error: Could not write to the file '{new_filename}'.")


