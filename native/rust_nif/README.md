# NIF for rust_nif

## To compile the NIF in Erlang:

Add the following lines to your `rebar.config` file:
```erlang
{plugins, [rebar3_rustler]}.

{cargo_opts, [
    {src_dir, "native/rust_nif"}
]}.

{provider_hooks, [
    {pre, [
        {compile, {cargo, build}}
    ]},
    {post, [
        {clean, {cargo, clean}},
        {eunit, {cargo, test}}
    ]}
]}.
```

Build
-----

    $ cargo build

Test
-----

    $ cargo test
