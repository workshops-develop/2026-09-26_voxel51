# 2026-09-26_voxel51
2026-09-26_voxel51


## -

If you are attending a Voxel51 workshop, **using WSL (Windows Subsystem for Linux) is highly recommended** over native Windows, even though Voxel51 officially supports both.

While you can run FiftyOne perfectly fine on native Windows, the broader computer vision and machine learning ecosystem is built heavily around Linux. Using WSL 2 will save you from several common headaches during the workshop and in your future projects.

Here is why WSL is the better choice for this stack:

* **Python Multiprocessing:** FiftyOne runs its local web app via a separate background process. On native Windows, Python's multiprocessing requires you to strictly wrap your scripts in `if __name__ == '__main__':` to avoid crashing or spawning infinite processes. WSL handles multiprocessing natively like Linux, meaning standard scripts and notebooks run without needing Windows-specific modifications.
* **Dependency Management:** Many computer vision libraries that integrate with FiftyOne (like PyTorch, OpenEXR, or specific model binaries) are built for Linux first. Installing their pre-compiled wheels in WSL is trivial with `pip`, whereas native Windows often requires hunting down specific `.whl` files or dealing with C++ build tools.
* **Docker and Agents:** If the workshop covers advanced topics like running evaluation pipelines, building custom plugins, or deploying Vision Agents, you may need to use Docker. Docker Desktop on Windows runs natively through WSL 2 anyway, so having your FiftyOne environment already in WSL makes volume mounting and path management seamless.

**Recommendation for the Workshop:**
Install **WSL 2** with Ubuntu, set up your Python environment (using `venv` or `conda`) inside WSL, and access the code using VS Code's "WSL" extension. When you launch the FiftyOne App from WSL, it will automatically forward to your Windows browser at `http://localhost:5151`, giving you the performance of Linux with the convenience of your Windows desktop.
