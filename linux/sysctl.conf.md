# sysctl.conf

### Dissable IPv6 <a href="#dissable-ipv6" id="dissable-ipv6"></a>

add the following lines to\
`net.ipv4.conf.all.disable_ipv6 = 1`\
`net.ipv4.conf.default.disable_ipv6 = 1`

run `sysctl -p`

add the following line to `/etc/ssh/sshd_config`\
`AddressFamily inet`

run `systemctl restart sshd`

### Other <a href="#other" id="other"></a>

Turn on execshield\
`kernel.exec-shield=1`\
`kernel.randomize_va_space=1`

Enable IP spoofing protection\
`net.ipv4.conf.all.rp_filter=1`

Disable IP source routing\
`net.ipv4.conf.all.accept_source_route=0`

Ignoring broadcasts request\
`net.ipv4.icmp_echo_ignore_broadcasts=1`\
`net.ipv4.icmp_ignore_bogus_error_messages=1`

Make sure spoofed packets get logged\
`net.ipv4.conf.all.log_martians = 1`
