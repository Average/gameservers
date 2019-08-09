FROM averagegroup/rust:latest
LABEL maintainer="admin@average.group"

ENV server_port=28015
ENV server_tickrate=10
ENV server_hostname="Your Server Name"
ENV server_identity="my_server_identity"
ENV server_maxplayers=50
ENV server_worldsize=3000
ENV server_seed=50000
ENV server_saveinterval=600
ENV rcon_port=28016
ENV rcon_web=0
ENV rcon_password="YourPassword"
ENV logfile=gamelog.txt

WORKDIR /opt/rust
RUN wget -nc -O oxide.zip https://github.com/theumod/uMod.Rust/releases/download/2.0.4262/Oxide.Rust.zip && unzip -o oxide.zip

VOLUME [ "/opt/steamcmd", "/opt/rust/logs", "/opt/rust/server", "/opt/rust/oxide", "/opt/rust/RustDedicated_Data/Managed" ]
ENTRYPOINT [ "./RustDedicated", "-batchmode", "+server.port ${server_port}", "+server.tickrate ${server_tickrate}", "+server.hostname ${server_hostname}", "+server.identity ${server_identiy}", "+server.maxplayers ${server_maxplayers}", "+server.worldsize ${server_worldsize}", "+server.seed ${server_seed}", "+server.saveinterval ${server_saveinterval}", "+rcon.port ${rcon_port}", "+rcon.web ${rcon_web}", "+rcon.password ${rcon_password}", "+logfile ${logfile}" ]

EXPOSE ${server_port} ${rcon_port}
