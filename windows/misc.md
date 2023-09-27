# Misc

Misc

* Set partition or drive as read only
  * in CMD enter `diskpart` then `list disk`
  * find your drive then select it with `select disk <diskNum>`
  * Enter `Attributes disk add read-only` then `exit`
