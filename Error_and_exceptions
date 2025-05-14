def file_modifier():
    """
    Program that reads a file, modifies its content, and writes to a new file.
    Includes comprehensive error handling for file operations.
    """
    # Ask user for input filename
    input_filename = input("Enter the name of the file to read: ")
    
    try:
        # Try to open and read the input file
        with open(input_filename, 'r') as input_file:
            content = input_file.read()
            print(f"\nSuccessfully read file: {input_filename}")
            print(f"Original content length: {len(content)} characters")
            
            # Ask for modification type
            print("\nHow would you like to modify the content?")
            print("1. Convert to uppercase")
            print("2. Convert to lowercase")
            print("3. Add line numbers")
            print("4. Replace a word")
            
            choice = input("\nEnter your choice (1-4): ")
            
            # Modify content based on user choice
            if choice == '1':
                modified_content = content.upper()
                modification_type = "uppercase conversion"
            elif choice == '2':
                modified_content = content.lower()
                modification_type = "lowercase conversion"
            elif choice == '3':
                lines = content.split('\n')
                modified_content = '\n'.join(f"{i+1}. {line}" for i, line in enumerate(lines))
                modification_type = "line numbering"
            elif choice == '4':
                search_word = input("Enter word to replace: ")
                replace_word = input("Enter replacement word: ")
                modified_content = content.replace(search_word, replace_word)
                modification_type = f"replacing '{search_word}' with '{replace_word}'"
            else:
                print("Invalid choice. Using default (uppercase conversion).")
                modified_content = content.upper()
                modification_type = "uppercase conversion"
            
            # Ask for output filename
            output_filename = input("\nEnter the name for the modified file: ")
            
            try:
                # Try to write to the output file
                with open(output_filename, 'w') as output_file:
                    output_file.write(modified_content)
                    print(f"\nSuccess! Modified content ({modification_type}) written to: {output_filename}")
                    print(f"Modified content length: {len(modified_content)} characters")
            
            except IOError as e:
                print(f"\nError writing to file '{output_filename}': {e}")
                print("This may be due to insufficient permissions or disk space.")
            except Exception as e:
                print(f"\nUnexpected error during file writing: {e}")
    
    except FileNotFoundError:
        print(f"\nError: The file '{input_filename}' was not found.")
        print("Please check the filename and try again.")
    except PermissionError:
        print(f"\nError: You don't have permission to access '{input_filename}'.")
    except UnicodeDecodeError:
        print(f"\nError: '{input_filename}' contains characters that cannot be decoded.")
        print("This might not be a text file or it might use an unsupported encoding.")
    except IOError as e:
        print(f"\nI/O error occurred with file '{input_filename}': {e}")
    except Exception as e:
        print(f"\nUnexpected error: {e}")
        print("Please try again with a different file.")

if __name__ == "__main__":
    print("🖋️ File Modification Program with Error Handling 🧪\n")
    file_modifier()
