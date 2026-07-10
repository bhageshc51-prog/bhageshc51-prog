from pathlib import Path
src = Path("/mnt/data/README_4(1).md").read_text(encoding="utf-8")
start = src.index("## 📊 GitHub Stats")
end = src.index("## 🔗 Connect With Me")
replacement = """## 📊 GitHub Profile

<div align="center">

![Profile Views](https://komarev.com/ghpvc/?username=bhageshc51-prog&color=7dd3fc&style=for-the-badge)
![Followers](https://img.shields.io/github/followers/bhageshc51-prog?style=for-the-badge&color=7dd3fc&labelColor=black)
![Stars](https://img.shields.io/github/stars/bhageshc51-prog?affiliations=OWNER&style=for-the-badge&color=7dd3fc&labelColor=black)

</div>

<br/>

"""
fixed = src[:start] + replacement + src[end:]
out = Path("/mnt/data/README_fixed.md")
out.write_text(fixed, encoding="utf-8")
print("Created:", out)
