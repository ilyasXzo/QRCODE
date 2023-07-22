
import qrcode

# Remplacez les informations ci-dessous par votre vCard
vcard_data = """
BEGIN:VCARD
VERSION:3.0
FN:Prénom Nom
TEL:0123456789
EMAIL:exemple@email.com
ADR:123 Rue du QR, Ville, Pays
END:VCARD
"""
# Créer le QR code
qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_L,
    box_size=10,
    border=4,
)
qr.add_data(vcard_data)
qr.make(fit=True)

# Créer une image QR code
img = qr.make_image(fill_color="black", back_color="white")

# Sauvegarder le QR code dans un fichier
img.save("vcard_qrcode.png")
