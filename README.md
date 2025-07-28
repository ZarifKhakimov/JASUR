from pathlib import Path

# Basic HTML template for a dark mode portfolio
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jasur Khakimjonov - Portfolio</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: #ffffff;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            text-align: center;
        }
        .container {
            max-width: 600px;
            padding: 20px;
        }
        h1 {
            font-size: 2.5em;
            color: #00ffcc;
        }
        p {
            font-size: 1.2em;
        }
        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 20px 0;
            border: 3px solid #00ffcc;
        }
        .skills {
            margin-top: 20px;
        }
        .skills span {
            display: inline-block;
            margin: 5px;
            padding: 5px 10px;
            background-color: #1e1e1e;
            border-radius: 5px;
            border: 1px solid #00ffcc;
            color: #00ffcc;
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://via.placeholder.com/150" alt="Profile Image" class="avatar">
        <h1>Jasur Khakimjonov</h1>
        <p>I'm an enthusiastic learner with a passion for technology, creativity, and innovation. I enjoy exploring new ideas and constantly improving myself.</p>
        <div class="skills">
            <h3>Skills & Interests</h3>
            <span>Web Design</span>
            <span>Creative Thinking</span>
            <span>Korean Language</span>
            <span>Football</span>
            <span>Coding Basics</span>
        </div>
    </div>
</body>
</html>
"""

# Save HTML file to a zip package
output_dir = Path("/mnt/data/jasur_portfolio")
output_dir.mkdir(parents=True, exist_ok=True)
html_path = output_dir / "index.html"

with open(html_path, "w", encoding="utf-8") as f:
    f.write(html_content)

# Zip the folder
zip_path = Path("/mnt/data/jasur_portfolio.zip")
import shutil
shutil.make_archive(str(zip_path).replace(".zip", ""), 'zip', output_dir)

zip_path.name

