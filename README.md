# python-week-5a

def modify_line(line):
    # Example modification: convert text to uppercase
    return line.upper()

def main():
    input_file = input("Enter the filename to read from: ")

    try:
        with open(input_file, 'r') as f:
            lines = f.readlines()

        # Modify content
        modified_lines = [modify_line(line) for line in lines]

        output_file = "modified_" + input_file
        with open(output_file, 'w') as f:
            f.writelines(modified_lines)

        print(f"✅ File processed successfully! Modified content written to '{output_file}'.")

    except FileNotFoundError:
        print("❌ Error: The file does not exist.")
    except PermissionError:
        print("❌ Error: You don't have permission to read this file.")
    except Exception as e:
        print(f"❌ Unexpected error
