# Introduction
File transfer script run in UEFI shell as simple as possible.

Source.py - File copy to.
```
python Source.py <host> <port> <file_path>
```

Sink.py - File copy from.
```
python Sink.py <port>
```

# Description
We do not want complex protocol and complex multitask process.

This just do simple file transfer.

Transfer done and stop script.

# Protocol
```
#pragma pack(1)
struct {
  UINT32 FileNameLenght;                    // Big endian
  UINT8  FileNameBuffer [FileNameLength];
  UINT32 FileLength;                        // Big endian
  UINT8  FileBuff [FileLength];
  UINT32 CRC32;                             // Big endian
}

```