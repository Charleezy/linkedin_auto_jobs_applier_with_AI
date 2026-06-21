#auto jobs applier
python .\runAiBot.py

#change lrf endings
dos2unix solution/solve.sh

# Start interactive container
uv run harbor tasks start-env --path harbor_tasks/hello-world --interactive

# Inside the container:
bash /solution/solve.sh  # Run your solution first
bash /tests/test.sh      # Then run tests

#Line endings use dos2unix to get all files in a directory and sub
#Can also just use dos2unix on a single file
find . -type f -print0 | xargs -0 dos2unix
