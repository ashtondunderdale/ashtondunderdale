```csharp
class BrainFuckInterpreter { static void Main() { string code =  "++++++++++[>+++++++>++++++++++>+++>+<<" +
"<<-]>++.>+.+++++++..+++.>++.<<+++++++++++++++.>.+++.------.--------.>+.>."; BrainFuck(code); } static void 
BrainFuck(string code) {  int i = 0, d = 0; byte[]  t = new byte[32767];  Stack<int> s = new(); while  (i <
code.Length) { char c = code[i]; switch (c) { case '>': case '<': d += (c == '>')? 1 : -1; i++; break; case 
'+': case '-': t[d] += (byte)((c == '+') ? 1 : -1); i++; break; case '.': Console.Write(Convert.ToChar(t[d]
)); i++; break; case ',': int iI = Console.Read(); if (iI == 13) { i++; continue; } t[d] = (byte)iI; break;
case '[': if (t[d] == 0) { int D = 1; while (D > 0) { i++; if (i >= code.Length) break; if (code[i] == '[') 
D++; else if (code[i] == ']') D--;  }  } else s.Push(i);  i++; break; case ']': if (t[d] != 0) i = s.Peek()
- 1; else  s.Pop(); i++;  break;  default:  Console.WriteLine($"Unknown command: {c}"); return;  }  }  }  }
```

