# FocusGuard — โฟกัสการ์ด

A cheat-resistant wrapper any teacher can generate for any assignment link.

Teachers paste an assignment link (Google Forms, quizzes, etc.) and get back a
protected link + QR code. Students open the protected link instead of the
original — it loads the real assignment in-frame, watches for tab/app
switches, and docks points for each one. Cross a configurable limit and the
screen locks until the teacher enters an unlock PIN. At the end, students get
an "integrity code" to paste into the assignment's last question, which the
teacher can decode back into a score + violation timeline.

Single self-contained HTML file (`index.html`), no backend, no build step,
no login. Works entirely client-side.

**Known limits (by design, not oversight):**
- Can't stop a student using a second device (phone, tablet) alongside the
  monitored one.
- Fullscreen enforcement is best-effort — iOS Safari doesn't support it at
  all, Android's is one swipe away. The core protection is
  `visibilitychange`/`blur` detection, which is reliable on both platforms.
- If the target site blocks iframe embedding (`X-Frame-Options: DENY`),
  the assignment may not load — students see a fallback notice.

This is a deterrent + evidence tool for classroom use, not a security system.

## Credits

QR code generation vendored from
[kazuhikoarase/qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator)
(MIT License).

## Live

https://greatestselfhelp.github.io/focusguard/
