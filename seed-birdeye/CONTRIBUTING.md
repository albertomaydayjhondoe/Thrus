# Contribuir
1. Restricciones de plataforma (innegociables): sin compilación Rust/C; prohibidos solders, solana-py, PyNaCl, cryptography. Criptografía = módulos puros verificados contra RFC.
2. Estilo: comentarios en español, identificadores técnicos en inglés.
3. `domain/` es puro: el test de arquitectura (tests/test_arquitectura.py) falla si importas I/O, framework o el reloj del sistema.
4. Todo PR debe: pasar pytest con cobertura de domain ≥90%, no introducir secretos (check_secrets en CI), y actualizar SPRINT_N.md si toca.
