# Lua Sender C API 
<!-- ---------------------------------------------------------------------------------------- -->

The *Sender C API* can be used to send asynchronous messages to native code running 
in other threads.

   * Lua objects implementing the *Sender C API* can send asynchronous messages.
   * Native C code invoking the *Sender C API* can read the asynchronous messages from any thread.

Lua objects implementing the *Sender C API* must
have an associated meta table entry *_capi_sender* delivered by
the C API function *sender_get_capi()* and the associated 
C API function *toSender()* must return a valid pointer for the given 
sender object. For further documentation see [sender_capi.h](./sender_capi.h).

<!-- ---------------------------------------------------------------------------------------- -->

### Implementations:

   * [mtmsg] buffer objects are implementing the *Sender C API*. If messages are added
     to the buffer, native C code can read the message from this buffer by invoking
     the *Sender C API*.

### Invocations:

   * [auproc] MIDI sender processor objects are sending midi messages that are given by a 
     registered sender object to an [auproc-capi] connector, see [auproc.new_midi_sender()] 
     and [ljack/example04.lua].

   * [auproc] AUDIO sender processor objects are sending audio samples that are given by a 
     registered sender object to an [auproc-capi] connector, see [auproc.new_audio_sender()] 
     and [ljack/example08.lua].

<!-- ---------------------------------------------------------------------------------------- -->

[mtmsg]:                     https://github.com/osch/lua-mtmsg

[ljack]:                     https://github.com/osch/lua-ljack
[ljack/example04.lua]:       https://github.com/osch/lua-ljack/blob/master/examples/example04.lua
[ljack/example08.lua]:       https://github.com/osch/lua-ljack/blob/master/examples/example08.lua

[auproc]:                    https://github.com/osch/lua-auproc
[auproc-capi]:               https://github.com/lua-capis/lua-auproc-capi
[auproc.new_midi_sender()]:  https://github.com/osch/lua-auproc/blob/master/doc/README.md#auproc_new_midi_sender
[auproc.new_audio_sender()]: https://github.com/osch/lua-auproc/blob/master/doc/README.md#auproc_new_audio_sender


<!-- ---------------------------------------------------------------------------------------- -->

## License 

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this
software, either in source code form or as a compiled binary, for any purpose,
commercial or non-commercial, and by any means.

<!-- ---------------------------------------------------------------------------------------- -->
