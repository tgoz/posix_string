# String replacement and templating in posix shell

Believed to be compatible with Bourne (posix), ash, dash, bash, zsh, and probably other similar shells.

## Examples

    # define functions
    . ./replace
    . ./apply_template

    echo -n "Input string" | replace t T
    
    echo -n 'pid={{$$}}' | apply_template
    
    cat <<'EOF' | apply_template
    Document generated at {{$(date)}}

    User {{${USERNAME}""}} has uid={{$UID}}.

    PID={{$$}}
    EOF
