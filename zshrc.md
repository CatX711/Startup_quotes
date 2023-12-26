Paste this code into your zshrc file (yes im on mac B^| )

<br />
<br />

```shell
# display every time a new terminal opened
# echo "( ._.) - Coding tip: Never code in Haskell"

# Function to display a random quote
display_random_quote() {
    local quotes_file="$HOME/quotes.txt"

    if [ -f "$quotes_file" ]; then
        local num_lines=$(wc -l < "$quotes_file")
        if [ "$num_lines" -gt 0 ]; then
            local random_line=$((RANDOM % num_lines + 1))
            sed -n "${random_line}p" "$quotes_file"
            echo  # Add a newline after each quote
            return
        fi
    fi
    echo "No quote available."
}

# Display a random quote when the terminal starts
display_random_quote

```
