# Erlang

Example of functional programming + pattern matching to find and replace an array item

```erlang
% snippet of a master/slave program
% The master should detect the fact that a slave process dies, restart it and print a message that it has done so.

master_loop(Slaves) ->
    receive
        {'EXIT', Pid, _Reason} ->
            master_loop(replace(Pid, Slaves, 1));
    end.

slave_init(N) ->
    slave_loop(N).

slave_loop(N) ->
    receive
        die ->
            ok;
        Msg ->
            io:format("Slave ~p got message ~p~n", [N, Msg]),
            slave_loop(N)
    end.

replace(Pid, [Pid | Rest], N) ->
    io:format("master restarting dead slave ~p~n", [N]),
    [spawn_link(fun() -> slave_init(N) end) | Rest];
replace(Pid, [Otherpid | Rest], N) ->
    [Otherpid | replace(Pid, Rest, N + 1)].
```
