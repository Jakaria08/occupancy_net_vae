import os
import sys
import trimesh

def convert_ply_to_off(input_dir, output_dir):
    # Ensure output directory exists
    os.makedirs(output_dir, exist_ok=True)

    # Iterate over all files in the input directory
    for filename in os.listdir(input_dir):
        if filename.endswith('.ply'):
            input_filepath = os.path.join(input_dir, filename)
            output_filepath = os.path.join(output_dir, os.path.splitext(filename)[0] + '.off')

            # Load the .ply file
            mesh = trimesh.load(input_filepath)
            # Export to .off file
            mesh.export(output_filepath)

            print(f"Converted {input_filepath} to {output_filepath}")

if __name__ == "__main__":
    if len(sys.argv) != 3:
        print("Usage: python convert_ply_to_off.py <input_directory> <output_directory>")
        sys.exit(1)

    input_directory = sys.argv[1]
    output_directory = sys.argv[2]

    convert_ply_to_off(input_directory, output_directory)
