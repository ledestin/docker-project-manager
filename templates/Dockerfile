# This is a recipe for your dev environment for {{ project_name }}.
# Do not confuse it with your project's deployment Dockerfile.

# Your base dev image with your tools and configuration.
FROM botanicus/dev:latest

# Do any setup here.
#RUN ...

# Most of the projects have only one volume that matches the name of the project.
# For instance if I have project my-blog, then the top-level directory my-blog/
# will typically contain a nested my-blog directory.
#
# This is because the top-level directory contains various persistent data such as
# SSH keys and shell history, whereas the nested directory is just the Git repository
# of your project.
#
# Note also that this Dockerfile is not used only by Docker: it's also used by DPM.
#
# Docker doesn't support specifying host directory (and host port) through Dockerfile.
# Quite logically so: there must be no assumption about the host.
#
# However, DPM does dictates the structure, so it is making these assumptions.
# So if you specify VOLUME {{ project_name}} here, DPM by default will mount
# such volume to {{ project_name }} within the top-level {{ project_name }} directory.
VOLUME /root/.history
VOLUME /root/.ssh
VOLUME /root/{{ project_name }}

# Just like DPM dictates where the volumes gets mounted, all the exposed ports are also published.
#EXPOSE 3000
