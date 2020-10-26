# String replacement and templating in posix shell

Believed to be compatible with Bourne (posix), ash, dash, bash, zsh, and probably other similar shells.

Templating is driven by shell substitutions in {{ }}. Contents of substitution may be anything which can be echo'ed;
in particular, shell variables (e.g. ${VAR} ) and commands (e.g. $(date) ). Substitutions beginning with { or ending with }
should be quoted, or separated from the {{ }} delimiters with an empty quoted string.

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
