# Ivar

Ivar is a light weight wrapper around HTTPoison that provides a fluent and composable way to build http requests

## Usage

Add `ivar` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [{:ivar, "~> 0.1.0"}]
end
```

You can then start to build http requests in a fluent nature

```elixir
defmodule IvarExample do
  def send_some_request do
    Ivar.new(:post, "http://example.com")
      |> Ivar.put_auth(:bearer, "some_token")
      |> Ivar.put_body("{\"testing\": 123}", :json)
      |> Ivar.send
  end
end
```

